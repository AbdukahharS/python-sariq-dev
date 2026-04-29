# #10 IF-ELSE

{% embed url="<https://www.youtube.com/watch?v=QH5Q_dyj3dI>" %}

## TARMOQLANISH

Shu vaqtgacha yozgan dasturlarimizga e'tibor bersangiz, dasturimiz yuqoridan pastga qarab qatorma-qator bajarilib keldi. Bu chiziqli dastur deyiladi. Voqelikda esa aksar dasturlar ma'lum bir shart bajarilishi (yoki bajarilmaganiga) ko'ra kodning bir qismidan boshqa qismiga "sakrab" o'tishi tabiiy hol. Dasturlashda bu ***tarmoqlanish*** deb ataladi.&#x20;

![Tarmoqlanishga misol](https://1283015017-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-MGbkqs1tROquIT6oqUs%2F-MMYB3w5bqcxar0xuzi2%2F-MMcrT4AK37JNwfmXziF%2Ffig1.png?alt=media\&token=176c0f12-d46f-43cd-a374-19c69f3caf3a)

Ushbu darsimizda biz **`if`** operatori yordamida shunday shartlarni yozishni, tekshirishni va tekshiruv natijasiga ko'ra kodning turli qismlarini bajarishni o'rganamiz. &#x20;

## `if` OPERATORI

**`if`** so'zi ingliz tilidan **"agar"** deb tarjima qilinadi va deyarli barcha dasturlash tillarida shartlarni yozish uchun foydalaniladi.&#x20;

Keling quyidagi misolni ko'ramiz. Bizda `avtolar` ro'yxati bor:

```python
avtolar = ['audi','bmw','volvo','kia','hyundai']
```

Biz ro'yxatdagi har bil elementni katta harf bilan konsolga chiqarmoqchimiz. Bunda istisno sifatida "BMW" mashinasi nomini hamma harflarini katta bilan chiqarishimiz kerak.&#x20;

Demak quyidagi kodni yozamiz:&#x20;

```python
for avto in avtolar: # avtolar ichidadi har bir avto uchun ...
    if avto == 'bmw':  # ... agar avto bmw ga teng bo'lsa ...
        print(avto.upper()) # avto nomini hamma harflarini katta bilan yoz.
    else: # aks holda ... 
        print(avto.title()) # avto nomini faqat birinchi harfini katta bilann yoz.
```

Kodni tahlil qilaylik:

* 1-qatorda biz for tsiklini boshladik: *avto ichidagi har bir avto uchun.*
* 2-qatorda shart yozdik: *agar avto bmw ga teng bo'lsa* (bu yerda `==` belgisi tenglikni tekshirish belgisi hisoblanadi va **"`avto`** **`bmw` ga tengmi?"** deb o'qiladi).&#x20;
* 3-qator yuqoridagi shartning badani hisoblanadi va **faqatgina** shart bajarilgandagina ishga tushadi va avto nomini hamma harflarini katta bilan yozadi (`.upper()` metodi).&#x20;
* 4-qatorda yana bir yangi operator, **`else`** bilan tanishamiz. "**Else**" ingliz tilidan "**aks holda**" deb tarjima qilinadi va **`if`** sharti bajarilmaganda **`else`** qismi ichidagi kod bajariladi.&#x20;
* 5-qator esa `else` (aks holda, ya'ni 2- qatordagi shart bajarilmaganda) ishga tushadi va avto nomining faqat birinchi harfini katta bilan yozadi (`.title()` metodi)

{% hint style="danger" %}
**Diqqat!** Shart "badani" shartdan biroz o'ngga surib yoziladi (huddi `for` tsikli kabi). `if/else` dan keyin kelgan va o'ngga surib yozilgan har bir qator `if/else` shartining badani hisoblanadi.
{% endhint %}

Yuoqridagi kodni bajaramiz, va natijani ko'ramiz:

```python
avtolar = ['audi','bmw','volvo','kia','hyundai']
for avto in avtolar: # avtolar ichidadi har bir avto uchun ...
    if avto == 'bmw':  # ... agar avto bmw ga teng bo'lsa ...
        print(avto.upper()) # avto nomini hamma harflarini katta bilan yoz.
    else: # aks holda ... 
        print(avto.title()) # avto nomini faqat birinchi harfini katta bilan yoz.
```

Natija:

![](https://1283015017-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-MGbkqs1tROquIT6oqUs%2F-MMcxtx3m5yFtCQkecbx%2F-MMczNUKHUCFPNEElicg%2Fimage.png?alt=media\&token=fb639f61-464f-4ed0-a555-5fa75bb03103)

## TRUE/FALSE

Yuqorida shartni tekshirish uchun `==` operatoridan foydalandik. Bu operatorni oddiy tilga tarjima qilsak ***"tengmi?"*** degan ma'noni beradi.&#x20;

Agar shartning ikki tarafidagi qiymatlar teng bo'lsa ifoda **TRUE** qiymatini qaytaradi ("True" so'zi ingliz tilidan "haqiqiq" yoki "to'g'ri" deb tarjima qilinadi).

Aksincha, qiymatlar tenglik qanoatlantirilmasa, ifoda **FALSE** qiymatini qaytaradi ("False" so'zini ingliz tilidan "yolg'on" deb tarjima qilsak bo'ladi).

Quyidagi misollarga e'tibor bering. Biz `ism` degan o'zgaruvchi yaratdik, va unga `'Ali'` matnini yukladik. Keling endi `==` yordamida `ism` ning qiymatini tekshirib ko'ramiz:

![](https://1283015017-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-MGbkqs1tROquIT6oqUs%2F-MMd4_mGp7KhHljlqSbZ%2F-MMeM0VfegmFez43z3oQ%2Fimage.png?alt=media\&token=bab72ca9-5aaf-4ed0-a78c-84fe7a84004d)

Ko'rib turganingizdek avval `ism=='Ali'` (`ism` `'Ali'` ga tengmi?) deb so'raganimizda, ifoda `TRUE` (Ha) degan javobni qaytardi, keyin esa `ism=='Vali'` (`ism` `'Vali'` ga tengmi?) deb so'raganimizda esa, ifoda `FALSE` (Yo'q) deb qiymat qaytardi.

Demak, `if/else` bog'lamasida, `if` ning badani ifoda `True` bo'lganda, `else` ning badani esa ifoda `False` bo'lganda bajariladi.&#x20;

## MATNLARNI SOLISHTIRISH

Aksar tizimlar foydalanuvchi kiritgan matnni ma'lum bir ko'rinishga keltirib oladi. Buning sababi, kompyuter uchun `'Ali'`, `'ALI'`, va `'ali'` bu uchta turli hil ism. Ularni solishtirish uchun esa bir ko'rinishga keltirib olish kerak.

Tasavvur qiling siz yangi email manzil ochmoqchisiz, va o'zingizga yangi foydalanuvchi ismini tanlashingiz kerak. Kompyuter siz kiritgan foydalanuvchi ismini tizimdagi mavjud foydalanuvchilar bilan solishtiradi va agar ism band bo'lsa sizga boshqa ism tanlashni aytadi. Solishtirish jarayonida esa, siz tanlagan ismni kichik harflarga o'tkazib, boshqa ismlar bilan solishtiradi.

![Yandex.uz sahifasida ro'yxatdan o'tish jarayoni](https://1283015017-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-MGbkqs1tROquIT6oqUs%2F-MMeP_WLpHkdzcxiw2zi%2F-MMeU64riTA_t65PqoXr%2Fimage.png?alt=media\&token=67317e40-bfd0-4173-bd32-3c43d10f7a37)

Yuqoridagi misolda, kimdur <anvar@yandex.ru> manzilini band qilgan, agarda men `'Anvar'`, yoki `'ANvar'`, yoki `'ANVAR'` deb login tanlasam ham, <anvar@yandex.ru> band bo'gani sababli men so'ragan loginlar rad qilinaveradi.&#x20;

Xo'sh, turli ko'rinishda yozilgan matnlarni qanday qilib solishtiramiz? Juda oddiy. Matnlarni solishtirishdan avval `.lower()` metodi yordamida kichik harflar ko'rinishiga keltirib olamiz:

```python
ism = 'Ali'
ism.lower() == 'ali'
```

Natija: `True`

## QIYMATLARNING TENG EMASLIGINI TEKSHIRISH

Agar ikki qiymatning teng emasligini tekshirish talab qilinsa, `!=` operatoridan foydalanilamiz.&#x20;

```python
ism = input('Ismingiz nima?\n>>>') # Foydalanuvchi ismini so'raymiz
if ism.lower() != 'ali': # Agar ism Aliga teng bo'lmasa ...
    print(f"Uzr, {ism.title()} biz Alini kutayapmiz.") # quyidagi xabar chiqadi
else:
    print("Salom, Ali")
```

![Natija](https://1283015017-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-MGbkqs1tROquIT6oqUs%2F-MMeVadFwBXQmhe8UWVv%2F-MMeqY-wx5KUYWFaega3%2Fimage.png?alt=media\&token=1cad6bf3-0472-4244-b021-33eafc0db8bb)

Demak yuqoridagi kodning 2-qatorida `ism` ichidagi qiymat `'ali'` ga teng bo'lmasa *"Uzr, {ism} biz Alini kutyapmiz"* degan xabarni chiqar dedik. Aks holda (`else`), `"Salom, Ali"` degan xabar chiqadi.

{% hint style="info" %}
Shartlarda `else` qismi bo'lishi majburiy emas. Bunga keyingi bo'limlarda tushunarliroq misollar ko'ramiz.
{% endhint %}

## SONLARNI SOLISHTIRISH

Sonlarni solishtirishda yuqoridagi teng (`==`) va teng emas (`!=`) shartlariga qo'shimcha ravishda quyidagi mantiqiy shartlar ham qo'shiladi:

* Kichik: `a<b`
* Kichik yoki teng: `a<=b`
* Katta: `a>b`
* Katta yoki teng: `a>=b`

```python
javob = float(input("12x6 nechiga teng?>>>"))
if javob!=72:
    print("Javob xato!")
```

![Natija](https://1283015017-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-MGbkqs1tROquIT6oqUs%2F-MMeVadFwBXQmhe8UWVv%2F-MMewgPWSwRz8L_i122u%2Fimage.png?alt=media\&token=356090d2-ab38-4475-9cbf-149a177c3bcc)

```python
yosh = int(input("Yoshingiz nechida?>>>"))
if yosh>=18: # yosh 18 dan katta yoki teng bo'lsa
    print('Xush kelibsiz!')
else: # ask holda
    print('Kirish mumkin emas!')
```

![](https://1283015017-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-MGbkqs1tROquIT6oqUs%2F-MMexlh5oIQLjya6mLJZ%2F-MMey0qAvKQC3JlG-f8D%2Fimage.png?alt=media\&token=522c304a-05fd-406b-baf0-4e345549d6ea)

```python
login = input("Yangi login tanlang:")
if len(login)<=5: # login uzunligini tekshiramiz
    print("Login 5 harfdan ko'proq bo'lishi shart!")
```

![Natija](https://1283015017-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-MGbkqs1tROquIT6oqUs%2F-MMexlh5oIQLjya6mLJZ%2F-MMf-xwdyOFBTQcaNrUL%2Fimage.png?alt=media\&token=d8edee6a-881d-484e-b904-9ff9dee9bf46)

Sonlarni solishtirishda arifmetik ifodalar ham yozishimiz mumkin:

```python
yil = int(input("Tug'ilgan yilingizni kiriting:"))
if 2020-yil<18: # foydalanuvchining yoshini hisoblaymiz
    print(f"Yoshingiz {2020-yil}da ekan.")
    print("Kirish mumkin emas!")
else:
    print("Xush kelibsiz!")
```

![Natija](https://1283015017-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-MGbkqs1tROquIT6oqUs%2F-MMf1QCPb9Vah1fjvdWp%2F-MMf8QjPej7q6ji1ysU-%2Fimage.png?alt=media\&token=73cd19f2-736d-402e-8915-a5479854cb86)

## BIR QATOR `if/else`

Qisqa kodlar uchun shart va uning badanini 1 qatorga jamlab yozishimiz ham mumkin:

```python
yosh = int(input("Yoshingiz nechida?>>>"))
if yosh>65: print("Siz COVID-19 risk guruhida ekansiz")
```

![Natija](https://1283015017-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-MGbkqs1tROquIT6oqUs%2F-MMivFFF91Tt-vMDZPvL%2F-MMiwqXQb3zenzlMiWF0%2Fimage.png?alt=media\&token=5322866b-5bbc-415e-a076-1d504c73ed17)

Yoki:

```python
x, y = 25, 50 # x=25 va y=50
print("x>y") if x>y else print("x<y")
```

Natija: `x<y`

## AMALIYOT

* Yangi `cars = ['toyota', 'mazda', 'hyundai', 'gm', 'kia']` degan ro'yxat tuzing, ro'yxat elementlarining birinchi harfini katta qilib konsolga chqaring. GM uchun ikkala harfni katta qiling.

![](https://1283015017-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-MGbkqs1tROquIT6oqUs%2F-MMhtJcB6L6ViQaDjYOj%2F-MMhuWawX7du_nPXqnli%2Fimage.png?alt=media\&token=7f51babd-1ee5-4b71-afff-b6489ec25f58)

* Yuqoridagi mashqni teng emas (`!=`) operatori yordamida bajaring.&#x20;
* Foydalanuvchi login ismini so'rang. Agar login admin bo'lsa, *"Xush kelibsiz, Admin. Foydalanuvchilar ro'yxatini ko'rasizmi?"* xabarini konsolga chiqaring. Aks holda, *"Xush kelibsiz, `{foydalanuvchi_ismi}!`"*  matnini konsolga chiqaring.
* Foydalanuvchidan 2 ta son kiritishni so'rang. Agar ikki son bir-biriga teng bo'lsa, "Sonlar teng" ekan degan yozuvni konsolga chiqaring.
* Foydalanuvchidan istalgan son kiritishni so'rang. Agar son manfiy bo'lsa konsolga "Manfiy son", agar musbat bo'lsa "Musbat son" degan xabarni chiqaring.&#x20;
* Foydalanuvchidan son kiritishni so'rang, agar son musbat bo'lsa uning ildizini hisoblab konsolga chiqaring. Agar son manfiy bo'lsa, "Musbat son kiriting" degan xabarni chiqaring.&#x20;

## JAVOBLAR

{% embed url="<https://repl.it/@anvarbek/javoblar-10-dars#main.py>" %}


---

# Agent Instructions: Querying This Documentation

If you need additional information that is not directly available in this page, you can query the documentation dynamically by asking a question.

Perform an HTTP GET request on the current page URL with the `ask` query parameter:

```
GET https://python.sariq.dev/shartlar/10-if-else.md?ask=<question>
```

The question should be specific, self-contained, and written in natural language.
The response will contain a direct answer to the question and relevant excerpts and sources from the documentation.

Use this mechanism when the answer is not explicitly present in the current page, you need clarification or additional context, or you want to retrieve related documentation sections.
