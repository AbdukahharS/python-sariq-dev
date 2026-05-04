# #17 WHILE TSIKLI

<Embed url="https://www.youtube.com/watch?v=Wpp6tXpMGgM&feature=youtu.be" />

## YANA `input()`

Dasturlar foydalanuvchining muammolarini hal qilish uchun yoziladi. Buning uchun esa, foydalanuvchi bilan aloqa o'rnatish, undan turli ma'lumotlarni qabul qilib olib talab etiladi. Misol uchun, dasturimiz foydalanuvchiga ismi bilan murojat qilishi uchun, avval uning ismini so'rashi kerak. Yoki, foydalanuvchi istagan ma'lumotni topish uchun avval undan biror kalit so'z kiritishni so'rash kerak va hokazo.

Biz avvalgi darsimizda `input()` yordamida foydalanuvchidan qiymat qilishni o'rgangan edik. Dastur davomida `input()` funktsiyasini chaqirganimizda dastur foydalanuvchi biror matn kiritiib, Enter tugmasini bosgunga qadar to'xtab turadi.

Foydalanuvchi kiritgan qiymatni biror o'zgaruvchiga yuklash, va undan dastur davomida foydalanish mumkin.

```python
ism = input("Ismingiz nima? ")
print(f'Salom, {ism.title()}')
```

![Natija](../cirth-assets/e102a9a1-80ff-42c1-8400-16ebef9054d4.png)

input() finktsiyasi ichidagi matn ingliz tilida prompt, savol deyiladi. Aslida biz savolni ham o'zgaruvchiga yuklab, shaxsiy so'rovnomalar ham yaratishimiz mumkin.

```python
ism = input("Ismingiz nima? ")
savol = f"Salom, {ism.title()}. Yoshingiz nechida? "
yosh = input(savol)
```

![Natija](../cirth-assets/8dac2f29-628f-4d74-867e-abf2701be41e.png)

Yuqorida birinchi input() bilan foydalanuvchi ismini so'radik va yangi savol matnini yasab oldik.

### Sonlar va input()

`input()` funktsiyasi har qanday kiritilgan qiymatni matn sifatida qabul qilib oladi. Agar foydalanuvchidan son talab qilinsa, foydalanuvchi kiritgan qiymatni butun (integer) yoki on'lik (float) son ko'rinishiga o'tkazib olish kerak.

Buning uchun int() yoki float() funktsiyalaridan foydalanamiz.

```python
ism = input("Ismingiz nima? ")
savol = f"Salom, {ism.title()}. Yoshingiz nechida? "
yosh = input(savol)
yosh = int(yosh) # yosh ni butun songa o'tkazamiz
height = input("Bo'yingiz necha metr? ")
height = float(height) # bo'yni o'nlik songa o'tkazamiz
```

![Natija](../cirth-assets/7942bfe5-8fd4-4eae-be54-9bb372657800.png)

:::info
Foydalanuvchidan qiymat so'raganingizda input()ichidagi savolni aniq va tushunarli qilib yozing. Masalan: `input("Tug'ilgan yilingizni kiriting: ")`
:::

## `while` TSIKLI BILAN TANISHAMIZ

Biz avvalroq `for` tsikli bilan tanishgan edik. `for` tsikli ma'lum bir ro'yxatni olib, ro'yxat ichidagi qiymatlar tugaginga qadar biror kodni takrorlar edi. `while` ham takrorlash operatori bo'lib, `for` dan farqli ravishda, toki ma'lum bir shart to'g'ri (`True`) bo'lsa, kodni takrorlayveradi.

:::info
while so'zi ingiz tilidan "toki" yoki "-gacha" deb tarjima qilinadi.
:::

Keling sodda misol ko'ramiz, while yordamida 5 gacha sanaymiz:

```python
son = 1 # son ga 1 qiymatini beramiz
while son&lt;=5: # toki son 5 dan kichik yoki teng ekan...
    print(son, end=' ') # son ni konsolga chiqaramiz,
    son = son+1 # songa 1 qo'shamiz.
```

Natija: `1 2 3 4 5`

Yuqoridagi kodni tahlil qilamiz:

* avval `son` degan o'zgaruvchi yaratdik va unga `1` qiymatini berdik.
* 2-qatorda esa toki `son` 5 dan kichik yoki teng ekan 3-4-qatorlarni bajar dedik.
* 3-qatorda `son` ni konsolga chiqardik
* 4-qatorda `son` ga `1` qo'shdik.
* 4-qatordan so'ng kod yana 2-qatorga qaytadi va `son&lt;=5` shartini tekshiradi, agar shart bajarilsa 3-4 qator qayta-qayta bajarilaveradi.
* 5-qadamdan so'ng `son=5` bo'lganda `while` tsikli to'xtaydi.

:::info
Pythonda +\= operatori bor. Bu operator o'ng tarafdagi qiymatni chap tarafdagi qiymatga qo'shadi. Misol uchun, yuqorida `son = son + 1` o'rniga `son += 1` deb yozishimiz mumkin.
:::

## `while` va `input()`

Shu paytgacha yozgan dasturlarimiz faqatgina bir martta bajarilayotgan edi. while tsikli yordamida dasturni to'xtatish imkoniyatini foydalanuvchiga berishimiz mumkin.

```python
print("Kiritilgan sonning kvadratini qaytaruvchi dastur.")
savol = "Istalgan son kiriting "
savol += "(dasturni to'xtatish uchun 'exit' deb yozing): "
qiymat = ''
while qiymat != 'exit':
    qiymat = input(savol)
    if qiymat != 'exit':
        print(float(qiymat)**2)
```

![Natija](../cirth-assets/64c8db8b-c8ff-41b6-a704-5dab2736ddab.png)

Yuoqridagi dasturimiz toki foydalanuvchi `exit` deb yozguniga qadar takrorlanaveradi.

### Ishora (flag)

Yuqoridagi dasturda dasturni to'xtatish uchun yagona shartni tekshirdik (qiymat!\='exit'), katta dasturlarda bir emas bir nechta shartlarni tekshirish, va ulardan biri bajarilgan taqdirda dasturni to'xtatish talab qilinishi mumkin.

Bunday holatlarda biror o'zgaruvchidan ishora (flag) sifatida foydalanishimiz mumkin. Agar dastur bajarilishi davomida dasturni to'xtatish shartlaridan biri bajarilganda ishora o'zgaruvchining qiymatini o'zgartiramiz va dastur o'z-o'zidan to'xtaydi.

```python
print("Kiritilgan sonning kvadratini qaytaruvchi dastur.")
savol = "Istalgan son kiriting "
savol += "(dasturni to'xtatish uchun 'exit' deb yozing): "
ishora = True
while ishora:
    qiymat = input(savol)
    if qiymat == 'exit':
        ishora = False
    else:
        print(float(qiymat)**2)
```

## BREAK OPERATORI

`Break` operatori yordamida ma'lum bir shartni tekshirish va `while` tsikli bajarilishini to'xtatib qo'yish mumkin.

```python
print("Kiritilgan sonning kvadratini qaytaruvchi dastur.")
savol = "Istalgan son kiriting "
savol += "(dasturni to'xtatish uchun 'exit' deb yozing): "

while True: # abadiy tsikl
    qiymat = input(savol)
    if qiymat == 'exit':
        break # tsiklni to'xtatish
    else:
        print(float(qiymat)**2)
```

`Break` operatori `for` tsiklini to'xtatish uchun ham ishlatiladi.

```python
sonlar = list(range(1,11))
for son in sonlar: 
    if son == 5: # son 5 ga teng bo'lsa kod to'xtaydi
        break
    print(f"{son} ning kvadrati {son**2} ga teng")
```

![Natija](../cirth-assets/b56c0471-2573-4e49-b242-0d3d899af7af.png)

:::info
`while` tsikli ichida bir nechta `break` operatori ham bo'lishi mumkin.
:::

## CONTINUE OPERATORI

`Continue` operatori esa aksincha, ma'lum bir shart bajarilganda qadam tashlab o'tish uchun mo'ljallangan.

```python
sonlar = list(range(1,11))
for son in sonlar:
    if son == 5: # son 5 ga teng bo'lsa tiskl boshiga qaytadi
        continue
    print(f"{son} ning kvadrati {son**2} ga teng")
```

![Natija: 5 ning kvadrati qani?](../cirth-assets/22d39cd0-f2df-4501-bce8-7fba7254d03e.png)

```python
son = 0
while son&lt;10:
    son += 1
    if son%2!=0:
        continue
    else:
        print(son)
```

:::info
`while` tsikli ichida bir nechta `continue` operatori ham bo'lishi mumkin.
:::

## ABADIY TSIKL TUZOG'I

Tsikllar bilan ishlashda abadiy tsikl yaratib qo'yishdan ehtiyot bo'lishimiz kerak. Abadiy tsiklga turli mantiqiy xatolar sabab bo'lishi mumkin: noto'g'ri shart, o'zgarmas qiymat, kodlar ketma-ketligida xatolik va hokazo.

Kelin ba'zi misollarni ko'ramiz:

```python
# infinite loop
son = 0
while son&lt;10:
    if son%2!=0:
        continue
    else:
        print(son)
```

Yuqoridagi kod abadiy davom etadi, sababi biz `son` ning qiymatini o'zgartirishni esdan chiqardik.

```python
son = 0
while son&lt;10:    
    if son%2!=0:
        continue
    else:
        print(son)
    son += 1
```

Bu kod ham abadiy davom etadi, lekin nima uchun?

```python
son = 1
while son>0: 
    son += 1
    if son%2!=0:
        continue
    else:
        print(son)
```

Yuqoridagi kodda esa xato shart tufayli (`son>0`) kod abadiy aylanadi.

:::danger
Dastur bajarilishini to'xtatish uchun konsolda **Ctrl+C** tugmasini bosing
:::

## AMALIYOT

1. Foydalanuvchidan yaxshi ko'rgan kitoblarini kiritishni so'rang. Foydalanuvchi `stop` so'zini yozishi bilan dasturni to'xtating
2. Muzeyga chipta narhi foydalanuvchining yoshiga bog'liq: 7 dan yoshlarga - 2000 so'm, 7-18 gacha 3000 so'm, 18-65 gacha 10000 so'm, 65 dan kattalarga bepul. Shunday while tsikl yozingki, dastur foydalanuvchi yoshini so'rasin va chipta narhini chiqarsin. Foydalanuvchi `exit` yoki `quit` deb yozganda dastur to'xtasin (ikkita shartni ham tekshiring).
   1. Yuqoridagi dasturni turli usullarda yozib ko'ring (break, ishora, yoki shart tekshirish)
3. Quyidagi dasturda bir nechta mantiqiy xatolar bor. Jumladan, xusisiy holatlarda tsikl abadiy qaytarilib qolmoqda. Xatolarni to'g'rilay olasizmi?

```python
savol ="Kiritilgan sonning ildizini qaytaruvchi dastur.\n"
savol += "Musbat son kiriting "
savol += "(dasturni to'xtatish uchun 'exit' deb yozing): "

while True:
    qiymat = input(savol)
    if qiymat&lt;0:
        continue
    elif qiymat=='Exit':
        break
    else:
        ildiz = float(qiymat)**(0.5)
        print(f"{qiymat} ning ildizi {ildiz} ga teng")
```

## JAVOBLAR

### GitHub

<Embed url="https://github.com/anvarnarz/python-darslar" />

### Repl.it

<Embed url="https://repl.it/@anvarbek/javoblar-17-01#main.py" />

<Embed url="https://repl.it/@anvarbek/javoblar-17-02" />

<Embed url="https://repl.it/@anvarbek/javoblar-17-03" />