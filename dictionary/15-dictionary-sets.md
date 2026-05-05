# #15 LUG'AT ELEMENTLARI BILAN ISHLASH

<Embed url="https://youtu.be/ArIW3EAtNF4" />

Avvalgi darsimizda lug'at bilan tanishdik, va lug'atdagi elementlarga kalit so'z bo'yicha murojat qilishni o'rgandik. Lug'atlar katta yoki kichik bo'lishi mumkin. Ba'zida lug'atdagi barcha kalitlarni yoki qiymatlarni bilmasligimiz mumkin. Bunday holatda qanday yo'l tutamiz?

Ushbu darsimizda lug'at elementlarini turli usullar yordamida chiqarishni o'rganamiz.

## `.items()` METODI

Ushbu metod yordamida lug'at ichidagi barcha kalit-qiymat juftliklarini ko'rishimiz mumkin.

```python
talaba_0 = {
    'ism':'alijon',
    'familiya':'shamshiyev',
    'yosh':22,
    'fakultet':'matematika',
    'kurs':4
    }

print(talaba_0.items())
```

Natija: `dict_items([('ism', 'alijon'), ('familiya', 'shamshiyev'), ('yosh', 22), ('fakultet', 'matematika'), ('kurs', 4)])`

Bu metodni to'g'ridan-to'g'ri emas, for tsikli yordamida chaqirish orqali lug'atdagi barcha elementlarni tushunarliroq shaklda ko'rishimiz mumkin.

```python
for kalit, qiymat in talaba_0.items():
    print(f"Kalit: {kalit}")
    print(f"Qiymat: {qiymat} \n")
```

![Natija](../cirth-assets/350102c9-0d4c-4657-8899-e1dde39a6c5b.png)

Yuoqirdagi kodda, `talaba_0` lug'atidagi har bir kalit va qiymat juftligini konslga chiqardik. E'tibor bering, `for` tsiklida biz bir emas ikkita o'zgaruvchi yaratib oldik (`kalit` va `qiymat`).

Bu usul ba'zi lug'atlardagi ma'lumotlarni chiroyli ko'rinishda chiqarish uchun juda qo'l keladi.

```python
telefonlar = {
    'ali':'iphone x',
    'vali':'galaxy s9',
    'olim':'mi 10 pro',
    'orif':'nokia 3310'
    }

for k, q in telefonlar.items():
    print(f"{k.title()}ning telefoni {q}")
```

![Natija](../cirth-assets/6c24089f-8f4e-42e5-ae60-9669003f47b3.png)

## `.keys()` METODI

Agar lug'atdagi kalit so'zlarni ko'rish talab qilinsa, .keys() metodidan foydalanishimiz mumkin.

```python
mahsulotlar = { # Do'kondagi mahsulotlar
    'olma':10000,
    'anor':20000,
    'uzum':40000,
    'anjir':25000,
    'shaftoli':30000
    }

print(mahsulotlar.keys())
```

Natija: `dict_keys(['olma', 'anor', 'uzum', 'anjir', 'shaftoli'])`

```python
print('Do\'kondagi mahsulotlar:')
for mahsulot in mahsulotlar.keys():
    print(mahsulot.title())
```

![Natija](../cirth-assets/fa2235fd-0c96-4a20-b8c5-e4ac2031ba15.png)

:::info
Yuqoridagi kodimizda, `for` tsiklida `.keys()` metodini ishlatmasak ham huddi shu natija chiqadi.
:::

`for` tsikli va `if` sharti yordamida lug'atdagi biror qiymatlarni alohida chiqarishimiz ham mumkin:

```python
bozorlik = ['anor','uzum','non','baliq']
for mahsulot in mahsulotlar:
    if mahsulot in bozorlik:
        print(f"{mahsulot.title()} {mahsulotlar[mahsulot]} so'm")
```

![Natija](../cirth-assets/5b706f2e-9e14-4cbc-9cf8-d3368207bb2b.png)

Yuqordagi kodga e'tibor bering. Biz avval `borolik` degan ro'yxat yaratdik (uyga bozor qilyapmiz), keyin esa `mahsulotlar` lug'atidagi har bir mahsulotni bizdagi `bozorlik` ro'yxati bilan solishtirdik. Agar mahsulot bizning `bozorlik` ro'yxatimizda bo'lsa, uning narhini konsolga chiqardik.

Quyidagi misolda esa aksincha, bozorlik ro'yxatidagi har bir elementni do'kondagi mahsulotlar bilan solishtiramiz, va mahsulot do'konda yo'q bo'lsa, do'konga murojat qoldiramiz:

```python
for buyum in bozorlik:
    if buyum not in mahsulotlar:
        print(f"Iltimos, do'koningizga {buyum} ham olib keling")
```

![Natija](../cirth-assets/8e122e13-c594-4ff6-813c-419ef40601b0.png)

### LUG'AT ELEMENTLARINI TARTIB BILAN CHIQARISH

Pythonda lug'at elementlari siz (foydalanuvchi) kiritgan tartibda saqlanadi. Agar lug'at elementlarini alifbo bo'yicha chiqarish talab qilinsa, sorted() funktsiyasidan foydalanamiz.

```python
print("Do'konimizdagi mahsulotlar:")    
for mahsulot in sorted(mahsulotlar):
    print(mahsulot.title())
```

![Natija](../cirth-assets/3428c2b3-78c9-4c0d-bd21-6def7a1258a7.png)

## `.values()` METODI

Agar lug'atdagi qiymatlarni chiqarish talab qilinsa .values() metodidan foydalanishimiz mumkin.

```python
print(telefonlar.values())
```

Natija: `dict_values(['iphone x', 'galaxy s9', 'mi 10 pro', 'nokia 3310']`

```python
print('Foydalanuvchilar quyidagi telefonlarni ishlatishadi:')
for tel in telefonlar.values():
    print(tel)
```

![Natija](../cirth-assets/c94cd851-2202-4b47-a519-06123eeb5d9d.png)

Yuqoridagi usul bilan qiymatlarni chiqrganimizda, lug'atdagi barcha qiymatlar chiqib keladi. Agar, biror qiymat ko'p marta qaytarilsa, konsolga ham ko'p marta chiqib keladi.

Quyidagi misloni ko'raylik:

```python
telefonlar = {
    'ali':'iphone x',
    'vali':'galaxy s9',
    'olim':'mi 10 pro',
    'orif':'nokia 3310',
    'hamida':'galaxy s9',
    'maryam':'huawei p30',
    'tohir':'iphone x',
    'umar':'iphone x'    
    }

print('Foydalanuvchilar quyidagi telefonlarni ishlatishadi:')
for tel in telefonlar.values():
    print(tel)
```

![Natija](../cirth-assets/ced206ff-3691-4bec-99c4-fcf3a670e155.png)

Yuoqirdagi natijaga e'tibor bersanigz, bir nechta foydalanuvchilar **iphone x** va **galaxy s9** telefonidan foydalanishar ekan, va bu modellar qayta-qayta konsolga chiqdi.

Buning oldini olish uchun `set()` funktsiyasidan foydalanishimiz mumkin.

```python
print('Foydalanuvchilar quyidagi telefonlarni ishlatishadi:')
for tel in set(telefonlar.values()):
    print(tel)
```

![Natija](../cirth-assets/0152c607-dfc3-4cb3-aaa1-c6ae47e6387f.png)

:::info
Pythonda `set` yana bir ma'lumot turi bo'lib, ro'yxat va lug'at kabi bir nechta elementlarni saqlashga mo'ljallangan. Lug'at va ro'yxatdan farqli ravishda, set ichidagi elementlar biror tartibda saqlanmaydi, va ularga indeks orqali murojat qilib bo'lmaydi. Shuningdek, set ichida bir hil elementlar bo'lmaydi.
:::

## AMALIYOT

- Python izohli lug'atini yarating va lug'atga kamida 10 ta so'z qo'shing. Lug'atdagi har bir kalit va qiymatni for tsikli yordamida, alifbo ketma-ketligida chiroyli qilib konsolga chiqaring.

![Kutilgan natijaga misol](../cirth-assets/110a7ac0-3e71-4af9-953a-f284168586c3.png)

- Davlatlar va ularning poytaxtlari lug'atini tuzing. Avval lug'atdagi davlatlarni, keyin poytaxtlarni alohida-alohida, alifbo ketma-ketligida konsolga chiqaring.

![Kutilgan natijaga misol](../cirth-assets/a31660a3-15ce-4768-a2d7-95125f60be52.png)

- Foydalanuvchidan istalgan davlatni kiritishni so'rang va shu davlatning poytaxtini konsolga chiqaring. Agar foydalanuvchi lug'atda yo'q davlatni kiritsa, "Bizda bunday ma'lumot yo'q" degan xabarni chiqaring.

![Kutilgan natijaga misol](../cirth-assets/d95db2d5-cb88-4711-b9db-626929bb724f.png)

- Restoran menusi lug'atini tuzing (kamida 10 ta taom-narh juftligini kiriting). Foydalanuvchidan 3 ta ovqat buyurtma berishni so'rang. Foydalanuvchi kiritgan taomlarni menu bilan solishtiring, agar taom menuda bo'lsa narhini ko'rsating, aks holda "bizda bunday taom yo'q" degan xabarni chiqaring.

![Kutilgan natijaga misol](../cirth-assets/7dbcd9d0-9cfa-4a3e-a0d8-16df71b22714.png)

## JAVOBLAR

JAvoblarni [GitHub repositoryda](https://github.com/anvarnarz/python-darslar) yoki Repl.it sahifamizda ko'rishingiz mumkin.

### GitHub

<Embed url="https://github.com/anvarnarz/python-darslar" />

### Repl.it

<Embed url="https://repl.it/@anvarbek/javoblar-15-dars-01#main.py" />

<Embed url="https://repl.it/@anvarbek/javoblar-15-dars-02-03#main.py" />

<Embed url="https://repl.it/@anvarbek/javoblar-15-dars-04#main.py" />
