# #15 LUG'AT ELEMENTLARI BILAN ISHLASH

{% embed url="<https://youtu.be/ArIW3EAtNF4>" %}

Avvalgi darsimizda lug'at bilan tanishdik, va lug'atdagi elementlarga kalit so'z bo'yicha murojat qilishni o'rgandik. Lug'atlar katta yoki kichik bo'lishi mumkin. Ba'zida lug'atdagi barcha kalitlarni yoki qiymatlarni bilmasligimiz mumkin. Bunday holatda qanday yo'l tutamiz?&#x20;

Ushbu darsimizda lug'at elementlarini turli usullar yordamida chiqarishni o'rganamiz.

## `.items()` METODI

Ushbu metod yordamida lug'at ichidagi barcha kalit-qiymat juftliklarini ko'rishimiz mumkin.&#x20;

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

![Natija](https://1283015017-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-MGbkqs1tROquIT6oqUs%2F-MNg_JO_hqeM2MWS4Fui%2F-MNggiVPXVuciLOgSZNr%2Fimage.png?alt=media\&token=9f3fcf9e-6df1-4e1b-8279-0d1fdb426b5e)

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

![Natija](https://1283015017-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-MGbkqs1tROquIT6oqUs%2F-MNg_JO_hqeM2MWS4Fui%2F-MNghg8x2TD37b7PDZ8X%2Fimage.png?alt=media\&token=85ef5f8c-f4a1-4f5a-aeb8-da32f6d810ea)

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

![Natija](https://1283015017-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-MGbkqs1tROquIT6oqUs%2F-MNg_JO_hqeM2MWS4Fui%2F-MNgmjhB7f6522gb_qQp%2Fimage.png?alt=media\&token=4c8f02da-6880-4996-8060-48b67d0ecdb2)

{% hint style="info" %}
Yuqoridagi kodimizda, `for` tsiklida `.keys()` metodini ishlatmasak ham huddi shu natija chiqadi.
{% endhint %}

`for` tsikli va `if` sharti yordamida lug'atdagi biror qiymatlarni alohida chiqarishimiz ham mumkin:

```python
bozorlik = ['anor','uzum','non','baliq']
for mahsulot in mahsulotlar:
    if mahsulot in bozorlik:
        print(f"{mahsulot.title()} {mahsulotlar[mahsulot]} so'm")
```

![Natija](https://1283015017-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-MGbkqs1tROquIT6oqUs%2F-MNg_JO_hqeM2MWS4Fui%2F-MNgkofDwlP-EAeMnZ2r%2Fimage.png?alt=media\&token=5bb8f6f4-b569-4169-9066-782858c76970)

Yuqordagi kodga e'tibor bering. Biz avval `borolik` degan ro'yxat yaratdik (uyga bozor qilyapmiz), keyin esa `mahsulotlar` lug'atidagi har bir mahsulotni bizdagi `bozorlik` ro'yxati bilan solishtirdik. Agar mahsulot bizning `bozorlik` ro'yxatimizda bo'lsa, uning narhini konsolga chiqardik.

Quyidagi misolda esa aksincha, bozorlik ro'yxatidagi har bir elementni do'kondagi mahsulotlar bilan solishtiramiz, va mahsulot do'konda yo'q bo'lsa, do'konga murojat qoldiramiz:

```python
for buyum in bozorlik:
    if buyum not in mahsulotlar:
        print(f"Iltimos, do'koningizga {buyum} ham olib keling")
```

![Natija](https://1283015017-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-MGbkqs1tROquIT6oqUs%2F-MNg_JO_hqeM2MWS4Fui%2F-MNgnrZM-h2YkarCrrrr%2Fimage.png?alt=media\&token=351fa895-c7bb-44e5-8625-1c122cc46082)

### LUG'AT ELEMENTLARINI TARTIB BILAN CHIQARISH

Pythonda lug'at elementlari siz (foydalanuvchi) kiritgan tartibda saqlanadi. Agar lug'at elementlarini alifbo bo'yicha chiqarish talab qilinsa, sorted() funktsiyasidan foydalanamiz.

```python
print("Do'konimizdagi mahsulotlar:")    
for mahsulot in sorted(mahsulotlar):
    print(mahsulot.title())
```

![Natija](https://1283015017-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-MGbkqs1tROquIT6oqUs%2F-MNg_JO_hqeM2MWS4Fui%2F-MNgofYwolTO9GFvBEjB%2Fimage.png?alt=media\&token=99a19e67-be87-4a85-869d-2ca37e6d7e4f)

## `.values()` METODI

Agar lug'atdagi qiymatlarni chiqarish talab qilinsa .values() metodidan foydalanishimiz mumkin.&#x20;

```python
print(telefonlar.values())
```

Natija: `dict_values(['iphone x', 'galaxy s9', 'mi 10 pro', 'nokia 3310']`

```python
print('Foydalanuvchilar quyidagi telefonlarni ishlatishadi:')
for tel in telefonlar.values():
    print(tel)
```

![Natija](https://1283015017-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-MGbkqs1tROquIT6oqUs%2F-MNg_JO_hqeM2MWS4Fui%2F-MNgpaTyEMgk9EaDcwjJ%2Fimage.png?alt=media\&token=0a1811a6-5484-44d5-80b6-11dcda0174ee)

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

![Natija](https://1283015017-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-MGbkqs1tROquIT6oqUs%2F-MNg_JO_hqeM2MWS4Fui%2F-MNgqhVwuvyYEg_bjo7p%2Fimage.png?alt=media\&token=1d1457a0-6796-453e-9527-77b28e2bf82a)

Yuoqirdagi natijaga e'tibor bersanigz, bir nechta foydalanuvchilar **iphone x** va **galaxy s9** telefonidan foydalanishar ekan, va bu modellar qayta-qayta konsolga chiqdi.&#x20;

Buning oldini olish uchun `set()` funktsiyasidan foydalanishimiz mumkin.

```python
print('Foydalanuvchilar quyidagi telefonlarni ishlatishadi:')
for tel in set(telefonlar.values()):
    print(tel)
```

![Natija](https://1283015017-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-MGbkqs1tROquIT6oqUs%2F-MNg_JO_hqeM2MWS4Fui%2F-MNgrri2Sg7ZTr-nl-Tp%2Fimage.png?alt=media\&token=1d36fb05-cd08-4276-8e94-ab977fdffdf2)

{% hint style="info" %}
Pythonda `set` yana bir ma'lumot turi bo'lib, ro'yxat va lug'at kabi bir nechta elementlarni saqlashga mo'ljallangan. Lug'at va ro'yxatdan farqli ravishda, set ichidagi elementlar biror tartibda saqlanmaydi, va ularga indeks orqali murojat qilib bo'lmaydi. Shuningdek, set ichida bir hil elementlar bo'lmaydi.
{% endhint %}

## AMALIYOT

* Python izohli lug'atini yarating va lug'atga kamida 10 ta so'z qo'shing. Lug'atdagi har bir kalit va qiymatni for tsikli yordamida, alifbo ketma-ketligida chiroyli qilib konsolga chiqaring.&#x20;

![Kutilgan natijaga misol](https://1283015017-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-MGbkqs1tROquIT6oqUs%2F-MNiI2tS7Q3KsI1pSflC%2F-MNiJqfgxoHAfgiCaO8b%2Fimage.png?alt=media\&token=2700001e-f32f-4cbf-b023-3d4722a6de3b)

* Davlatlar va ularning poytaxtlari lug'atini tuzing. Avval lug'atdagi davlatlarni, keyin poytaxtlarni alohida-alohida, alifbo ketma-ketligida konsolga chiqaring.&#x20;

![Kutilgan natijaga misol](https://1283015017-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-MGbkqs1tROquIT6oqUs%2F-MNiI2tS7Q3KsI1pSflC%2F-MNiKbOCp4q0M37kcXqq%2Fimage.png?alt=media\&token=c6a99890-e8f9-42cd-9cb1-2bde799a204b)

* Foydalanuvchidan istalgan davlatni kiritishni so'rang va shu davlatning poytaxtini konsolga chiqaring. Agar foydalanuvchi lug'atda yo'q davlatni kiritsa, "Bizda bunday ma'lumot yo'q" degan xabarni chiqaring.

![Kutilgan natijaga misol](https://1283015017-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-MGbkqs1tROquIT6oqUs%2F-MNiI2tS7Q3KsI1pSflC%2F-MNiMFqTfCba-zztFdqF%2Fimage.png?alt=media\&token=28ee060e-fd22-40e5-9f9c-4f62946ac0d1)

* Restoran menusi lug'atini tuzing (kamida 10 ta taom-narh juftligini kiriting). Foydalanuvchidan 3 ta ovqat buyurtma berishni so'rang. Foydalanuvchi kiritgan taomlarni menu bilan solishtiring, agar taom menuda bo'lsa narhini ko'rsating, aks holda "bizda bunday taom yo'q" degan xabarni chiqaring.

![Kutilgan natijaga misol](https://1283015017-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-MGbkqs1tROquIT6oqUs%2F-MNiI2tS7Q3KsI1pSflC%2F-MNiOagGFTFR_dnoSTLu%2Fimage.png?alt=media\&token=ad52502c-e071-4eec-ad04-1fc027306d4e)

## JAVOBLAR

JAvoblarni [GitHub repositoryda](https://github.com/anvarnarz/python-darslar) yoki Repl.it sahifamizda ko'rishingiz mumkin.

### GitHub

{% embed url="<https://github.com/anvarnarz/python-darslar>" %}

### Repl.it

{% embed url="<https://repl.it/@anvarbek/javoblar-15-dars-01#main.py>" %}

{% embed url="<https://repl.it/@anvarbek/javoblar-15-dars-02-03#main.py>" %}

{% embed url="<https://repl.it/@anvarbek/javoblar-15-dars-04#main.py>" %}

