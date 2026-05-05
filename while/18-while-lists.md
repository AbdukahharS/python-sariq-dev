# #18 WHILE, RO'YXATLAR VA LUG'ATLAR

<Embed url="https://www.youtube.com/watch?v=1XOYa0BlF54" />

Ro'yxatlar (lug'atlar) bilan ishlashda while tisklining foydalari juda ko'p. Misol uchun foydalanuvchidan bir nechta ma'lumotlarni qabul qilib olish, ro'yxatdan takrorlanuvchi qiymatlarni o'chirib tashlash yoki bir ro'yxatni ikkinchi ro'yxatga ko'chirishda while tsiklidan foydalanishimiz mumkin.

## `WHILE` YORDAMIDA RO'YXATNI TO'LDIRISH

Quyidagi dasturga e'tibor bering, avval ismlar degan bo'sh ro'yxat yaratib oldik. Keyin esa while tsikli yordamida foydalanuvchidan ro'yxatga ism qo'shishni so'raymiz. So'ngra foydalanuvchidan yana ism qo'shmoqchi yoki yo'q ekanin so'raymiz va foydalanuvchining javobiga ko'ra yoki while ni boshiga qaytamiz, yoki tsiklni to'xtatamiz.

```python
ismlar = []

print("Yaqin do'stlaringiz ro'yxatini tuzamiz.")
n=1 # ismlarni sanash uchun o'zgaruvchi
while True:
    savol = f"{n}-do'stingiz ismini kiriting:"
    ism = input(savol)
    ismlar.append(ism)
    javob = input("Yana ism qo'shasizmi? (ha/yo'q)")
    if javob =='ha':
        n+=1
        continue
    else:
        break
```

![Natija](../cirth-assets/fec3455a-b8d8-402f-a739-473e7abc367e.png)

```python
print("Do'stlaringiz ro'yxati:")
for ism in ismlar:
    print(ism.title())
```

![Natija](../cirth-assets/0ad6fa04-f74c-4389-bedd-812a2a790d2e.png)

## `WHILE` YORDAMIDA LUG'ATNI TO'LDIRISH

Yuqoridagi usul bilan lu'gatlarni ham shakllantirishimiz mumkin. Quyidagi kodda `ism` bu kalit, `yosh` esa klaitga mos keluvchi qiymat. `while` tsiklining davomiyligi esa `ishora` ning qiymatiga bog'liq.

```python
print("Do'stlaringiz yoshini saqlaymiz.")
dostlar = {}
ishora = True
while ishora:
    ism = input("Do'stingiz ismini kiriting: ")
    yosh = input(f"{ism.title()}ning yoshini kiriting: ")
    dostlar[ism] = int(yosh) # ism kalit, yosh qiymat
    
    javob = input("Yana ma'lumot qo'shasizmi? (ha/yo'q)")
    if javob == "yo'q":
        ishora = False

for ism, yosh in dostlar.items():
    print(f"{ism.title()} {yosh} yoshda")
```

![Natija](../cirth-assets/53392905-7f68-4645-9fb5-a2f967ed8a99.png)

## RO'YXAT ELEMENTLARINI O'CHIRISH

Avvalgi darslarimizning birida ro'yxat elementini o'chirish uchun `.remove(qiymat)` metodi bilan tanishgan edik. Esingizda bo'lsa, bu metod ro'yxatdan eng birinchi uchragan `qiymat`ni o'chiradi. Agar ro'yxatimizda ma'lum bir qiymat bir necha bor takrorlangan bo'lsa, ularning barchasini o'chirib tashlash uchun `while` tsiklidan foydalanishmiz mumkin.

```python
cars = ['lacetti','nexia','toyota','nexia','audi','malibu','nexia']
while 'nexia' in cars: # toki nexia cars ro'yxati ichida ekan...
    cars.remove('nexia') # nexia ni ro'yxatdan olib tashla
print(cars)
```

Natija: `['lacetti', 'toyota', 'audi', 'malibu']`

Yuqoridagi tsikl toki `cars` degan ro'yxatda `'nexia'` qiymati tugagunga qadar takrorlanaveradi.

## RO'YXATDAN RO'YXATGA ELEMENT KO'CHIRISH

Tasavvur qiling bizda ma'lum bir ro'yxat bor, biz ro'yxatdagi har bir element ustida biror amalni bajarib, uni birinchi ro'yxatdan ikkinchi ro'yxatga ko'chirib olmoqchimiz. Shunday holatlarda `while` tsikli juda qo'l keladi.

Quyidagi misolni ko'raylik. Bizda `talabalar` ro'yxati bor. `while` tsikli toki ro'yxatda talabalar bor ekan aylanaveradi. Tsikl ichida biz `.pop()` metodi yordamida talabaning ismini ro'yxatdan sug'urib oldik va foydalanuvchidan talabani baholashni so'radik. Talabaning ismi va bahosini lug'at elementi ko'rinishida saqlab qo'ydik (`talaba` - kalit, `baho` - qiymat).

```python
talabalar = ['hasan', 'husan', 'olim', 'botir']
baholangan_talabalar = {}
while talabalar:
    talaba = talabalar.pop()
    baho = input(f"{talaba.title()}ning bahosini kiriting: ")
    print(f"{talaba.title()} baholandi")
    baholangan_talabalar[talaba] = baho
```

![Natija](../cirth-assets/b3206c19-4e8d-4149-85d1-74a5d3ad5d6e.png)

Yuqorida biz while tsikli yordamida ro'yxat va lug'atlar ustida bajarish mumkin bo'lgan ba'zi misollarni ko'rdik. Albatta dasturlash davomida bundan boshqa holatlar ham uchrashi tabiiy.

## AMALIYOT

1. Foydalanuvchidan buyurtma qabul qiluvchi dastur yozing. Mahsulotlar nomini birma-bir qabul qilib, yangi ro'yxatga joylang.
2. e-bozor uchun mahsulotlar va ularning narhlari lug'atini shakllantiruvchi dastur yozing. Foydalanuvchidan lug'atga bir nechta elementlar (mahsulot va uning narhi) kiritishni so'rang.
3. Yuqoridagi ikki dasturni jamlaymiz. Foydalanuvchi buyurtmasi ro'yxatidagi har bir mahsulotni e-bozordagi mahsulotlar bilan solishitiring (tayyor ro'yxat ishlatishingiz mumkin). Agar mahsuot e-bozorda mavjud bo'lsa mahuslot narhini chiqaring, aks holda "Bizda bu mahsulot yo'q" degan xabarni kor'sating.

## JAVOBLAR

### GitHub

<Embed url="https://github.com/anvarnarz/python-darslar" />

### Repl.it

<Embed url="https://repl.it/@anvarbek/javoblar-18-01#main.py" />

<Embed url="https://repl.it/@anvarbek/javoblar-18-02#main.py" />

<Embed url="https://repl.it/@anvarbek/javoblar-18-03#main.py" />