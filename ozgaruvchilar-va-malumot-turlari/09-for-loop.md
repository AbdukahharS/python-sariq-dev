# #09 FOR TAKRORLASH OPERATORI

{% embed url="<https://www.youtube.com/watch?v=982dbRh0Efg>" %}

## `for` BILAN TANISHAMIZ

Dasturlash davomida kodimizning biror qismini bir necha marta takrorlash talab etilishi mumkin. Misol uchun, ro'yxat ichidagi har bir elementni alohida qatordan konsolga chiqarish, yoki bo'lmasa har bir elementni kvdartaga oshirish va hokazo.&#x20;

Mana shunday vaziyatlarda bizga **`for`** operatori yordam beradi. Dasturlashda bu **tsikl** (**loop**) deb ataladi.&#x20;

Keling quyidagi misolni ko'ramiz. Bizda mehmonlar ro'yxati bor, biz har bir mehmonning ismini yangi qatordan chiqarmoqchimiz. Buning uchun quyidagi kodni yozamiz:

```python
mehmonlar = ['Ali','Vali','Hasan', 'Husan','Olim']
for mehmon in mehmonlar:
    print(mehmon)
```

Natija:

`Ali`

`Vali`

`Hasan`

`Husan`

`Olim`

Keling, kodni tahlil qilaylik.&#x20;

* 1-qatorda biz `mehmonlar` degan ro'yxat yaratdik va uni mehmonlarning ismi bilan to'ldirdik.
* 2-qatorda `for` tsiklini bohladik. Bu qator Pythonga `mehmonlar` degan ro'yxatdan har bir elementini olib uni yangi, `mehmon` degan o'zgaruvchiga yuklashni buyuryapti (*o'zgaruvchiga istalgan nom berishingiz mumkin. Biz tushunarli bo'lishi uchun* `mehmon` *deb atadik*)
* 3-qatorda biz `mehmon` degan o'zgaruvchining qiymatini konsolga chiqardik. Bu tsikl to `mehmonlar` ro'yxatida elementlar tugagunga qadar takrorlanadi.

{% hint style="info" %}
"**For**" so'zi ingliz tilidan "**uchun**" deb tarjima qilinadi.
{% endhint %}

Yuqoridagi kodni oddiy tilga tarjima qilsak *"Mehmonlar ro'yxatidagi har bir mehmon **uchun** uning ismini konsolga chiqar"* degan ma'noni beradi.&#x20;

## `for` QANDAY ISHLAYDI

Keling yana bir misol ko'raylik.&#x20;

```python
mehmonlar = ['Ali','Vali','Hasan', 'Husan','Olim']
for mehmon in mehmonlar:
    print(f"Hurmatli {mehmon}, sizni 20 Dekabr kuni nahorga oshga taklif qilamiz")
    print("Hurmat bilan, Palonchiyevlar oilasi")
```

Natija:

![](https://1283015017-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-MGbkqs1tROquIT6oqUs%2F-MMPNxgNwPmiIwnqKZ-n%2F-MMPQyZT5FQp6KY-8-aY%2Fimage.png?alt=media\&token=0c8954a5-7c1b-4d45-a941-4e4ecbdae325)

Yuqoridagi kodda 2-qator bu tsikl boshi deyiladi. Aynan shu qator kodimiz nech marta takrorlanishini aniqlaydi. Bizning holatimizda tsikl `mehmonlar` ro'yxati ichidagi elementlar tugagunga qadar takrorlanadi. Tsikl boshlanishi ikki nuqta (`:`) bilan tugaydi. Undan keyingi 3 va 4-qatorlar bu tsiklning badani deyiladi. &#x20;

Tsikl badani surilish (indentation) bilan ajratiladi, ya'ni tsiklning takrorlanuvchi qismi asosiy koddan bir muncha o'ngroqqa surilgan bo'ladi. Agar biz mana shu surilishni tark qilsak kodimiz xato beradi:

```python
mehmonlar = ['Ali','Vali','Hasan', 'Husan','Olim']
for mehmon in mehmonlar:
print(f"Hurmatli {mehmon}, sizni 20 Dekabr kuni nahorga oshga taklif qilamiz")
print("Hurmat bilan, Palonchiyevlar oilasi\n")
```

Natija: **`IndentationError: expected an indented block`**

Ko'rib turganingizdek for dan keyingi qatorni o'ngga surmaganimiz uchun **indentation error** (surishda xatolik) degan xabarni oldik.

Shunigdek, ko'pchilik yo'l qo'yadigan yana bir xato, qo'shimcha qatorlarni surish esdan chiqishi:

```python
mehmonlar = ['Ali','Vali','Hasan', 'Husan','Olim']
for mehmon in mehmonlar:
    print(f"Hurmatli {mehmon}, sizni 20 Dekabr kuni nahorga oshga taklif qilamiz")
print("Hurmat bilan, Palonchiyevlar oilasi\n")
```

Natija:

![](https://1283015017-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-MGbkqs1tROquIT6oqUs%2F-MMPNxgNwPmiIwnqKZ-n%2F-MMPUnWYBNdp6X7_11Mx%2Fimage.png?alt=media\&token=45393130-8c29-421c-88bc-d567bdf87433)

Yuqoridagi kodimizda 4-qatorni o'ngga surmaganimiz uchun, Python bu qatorni tsikl tashqarisida deb qabul qildi va faqatgina 1 marta, tsikl tugaganidan so'ng bajardi.&#x20;

Huddi shu kabi agar takrorlanishi kerak bo'magan kodni tsikldan so'ng o'ngga surib qo'ysak Python bu qatorni tsiklning tarkibida deb hisoblab, qayta-qayta bajaradi:

```python
mehmonlar = ['Ali','Vali','Hasan', 'Husan','Olim']
for mehmon in mehmonlar:
    print(mehmon)
    
    print(mehmonlar) # bu qator tsikl tashqarisida bo'lishi kerak edi
```

![](https://1283015017-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-MGbkqs1tROquIT6oqUs%2F-MMPNxgNwPmiIwnqKZ-n%2F-MMPV_aHRkWeJtIwqwGW%2Fimage.png?alt=media\&token=6c4fe1f9-8225-41d4-be8b-8dd62a148409)

Yuoqirdagi misolda 5-qator o'ngga surilib qolgani uchun Python bu qatorni ham bir necha bor takrorlab, konsolga chiqardi. To'g'ri kod quyidagicha bo'ladi:

```python
mehmonlar = ['Ali','Vali','Hasan', 'Husan','Olim']
for mehmon in mehmonlar:
    print(mehmon)
    
print(mehmonlar)
```

## `for` YORDAMIDA SONLI RO'YXATLAR BILAN ISHLASH

Keling quyidagi misolni ko'ramiz

```python
sonlar = list(range(1,11))
for son in sonlar:
    print(f"{son} ning kvadrati {son**2} ga teng")
```

Natija:

![](https://1283015017-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-MGbkqs1tROquIT6oqUs%2F-MMPNxgNwPmiIwnqKZ-n%2F-MMPZMvGrHyynJZ4WQr7%2Fimage.png?alt=media\&token=2e0ccfce-f6a2-4ca3-96e7-7a5861fd30c3)

`for` yordamida yangi ro'yxat ham shakllantirish mumkin:

```python
sonlar = list(range(11)) # 1 dan 10 gacha sonlar ro'yxatini yaratamiz
sonlar_kvadrati =[] # bo'sh ro'yxat yaratamiz
for son in sonlar:  # sonlar dagi har bir son uchun
    sonlar_kvadrati.append(son**2) # uning kv.ni hisoblab, sonlar_kvadrati ga yuklaymiz

print(sonlar)
print(sonlar_kvadrati)
```

Natija:&#x20;

`[0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10]`

`[0, 1, 4, 9, 16, 25, 36, 49, 64, 81, 100]`

## `for` va `input()`

for operatori va input() funktsiyasini jamlab, ro'yxatni foydalanuvchidan olingan qiymatlar bilan to'ldirish mumkin:

```python
dostlar = [] # bo'sh ro'yxat
print("5 ta eng yaqin do'stingiz kim?")
for n in range(5): # n bu yerda 0 dan 4 gacha qiymatlar oladi
    dostlar.append(input(f"{n+1}-do'stingizning ismini kiriting: "))
print(dostlar)
```

Natija:

![](https://1283015017-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-MGbkqs1tROquIT6oqUs%2F-MMPaWvgJ__zmMdi1b7y%2F-MMT-gtwhVd0_teSQ415%2Fimage.png?alt=media\&token=c78b15e7-f2c9-4e22-806b-602dbee06a8c)

Kodni tahlil qilamiz:

* 1-qatorda bo'sh `dostlar` ro'yxatini yaratdik
* 2-qatorda ekranga `"5 ta eng yaqin do'stingiz kim?"` degan xabarni chiqardik
* 3-qatorda tsiklni boshladik. `range(5)` funktsiyasi 0 dan 5 gacha sonlar ketma-ketligini yaratadi `(0,1,2,3,4)` tsikl esa `n` shularning har biriga teng bo'lib chiqquncha davom etadi.&#x20;
* 4-qatorda tsikl badani kelgan. Bu yerda biz foydalanuvchidan `n+1` do'stingizni kiriting deb so'radik. Nima uchun `n+1` (`n` emas)? Sababi `n` 0 dan 4 gacha qiymatlarni oladi, foydalanuvchiga tushunarli bo'lishi uchun esa biz "0-do'stingizni ismini kiriting:" deb emas, balki `n+1` ya'ni 1-ismni kiriting deb murojat qilyapmiz.
* 5-qatorda shakllangan ro'yxatni konsolga chiqardik.

{% hint style="success" %}
**`for`** tsikli har qanday dasturlash tilining eng muhim qismlaridan hisoblanadi va biz bu operatoraga hali takror-takror qaytamiz.
{% endhint %}

## AMALIYOT

* Kamida 5 elementdan iborat ismlar degan ro'yxat tuzing, va ro'yxatdagi har bir ismga takrorlanuvchi xabar yozing
* Yuoqirdagi tsikl tugaganidan so'ng, ekranga "Kod `n` marta takrorlandi" degan xabarni chiqaring (`n` o'rniga kod necha marta takrorlanganini yozing)

![Kutilgan natija](https://1283015017-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-MGbkqs1tROquIT6oqUs%2F-MMPNxgNwPmiIwnqKZ-n%2F-MMP_FTr--cIleoE1pUk%2Fimage.png?alt=media\&token=e6ff5313-10db-4dd2-81f5-ca42284f0218)

* 10 dan 100 gacha bo'lgan toq sonlar ro'yxatini tuzing. Ro'yxatning xar bir elementining kubini yangi qatordan konsolga chiqaring.

![](https://1283015017-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-MGbkqs1tROquIT6oqUs%2F-MMPNxgNwPmiIwnqKZ-n%2F-MMP_u9IVOIxvkgaD4R7%2Fimage.png?alt=media\&token=26b4f01a-1487-4ef4-a1b4-b15a8ee0ec61)

* Foydalanuvchidan 5 ta eng sevimli kinolarini kiritshni so'rang, va `kinolar` degan ro'yxatga saqlab oling. Natijani konsolga chiqaring.
* Foydalanuvchidan bugun nechta odam bilan uchrashganini (suhbatlashganini) so'rang, va har bir suhbatlashgan odamning ismini birma-bir so'rab ro'yxatga yozing. Ro'yxatni konsolga chiqaring.

![](https://1283015017-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-MGbkqs1tROquIT6oqUs%2F-MMT2VK6SaNLN7fUnjkD%2F-MMT5AHMlvPnOvBAj5Cg%2Fezgif-3-cbc37adef5e6.gif?alt=media\&token=7b016282-f3fc-4806-b740-47d1a3ea2161)

## JAVOBLAR

{% embed url="<https://repl.it/@anvarbek/javoblar-09-dars#main.py>" %}

{% file src="<https://1283015017-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-MGbkqs1tROquIT6oqUs%2F-MMTSwYnrPbX6zVKWQyw%2F-MMTVWRHTohf2o4hsQDa%2Fjavoblar-09-dars.zip?alt=media&token=bc93cdd3-7385-43cb-a079-eb5cf7e30ba6>" %}
\#09-dars javoblar
{% endfile %}

