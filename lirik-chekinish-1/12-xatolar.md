# #12 XATOLAR BILAN ISHLASH

{% embed url="<https://www.youtube.com/watch?v=Zp8hhWN_qwQ&feature=youtu.be>" %}

## XATOLAR

Har qanday dasturchi kod yozishda xato qiladi. Ko'p yozgan odam esa ko'p xato qiladi va bu tabiiy. Ba'zi xatolarimiz Python tomonidan dastur bajarilishdan avvaloq aniqlanadi. Ba'zilari esa dastur bajarish jarayonida aniqlanib, dasturimiz to'xtab qoladi. Keling, bugun dasturlashni yangi boshlaganlar eng ko'p yo'l qo'yadigan xatolar bilan tanishamiz.

## **SyntaxError** - SINTEKS XATOLIK

Biz *syntax error* bilan [3-darsimizda ](https://python.sariq.dev/ilk-qadamlar/03-print)tanishgan edik. Bu eng ko'p uchraydigan xato bo'lib, odatda dasturlash tili qoidalariga amal qilmaslik natijasida kelib chiqadi. Aksar dasturlash muhitlari sintaks xatolikni dastur bajarilishidan avvaloq aniqlab, dasturchiga ishora beradi. Sintaks xatolik bor dasturni Python bajarmaydi.

```python
print "Hello World!"
```

Natija: **`SyntaxError: Missing parentheses in call to 'print'. Did you mean print("Hello World!")?`**

Odatda dasturlash muhiti xatoning turi bilan birga (SyntaxError), xato haqida qo'shimcha ma'lumot ham beradi (`Missing parentheses in call to 'print'. Did you mean print("Hello World!")?`). Agar ingliz tilini tushunmasangiz, [Google Translate](https://translate.google.com/?ui=tob\&sl=en\&tl=ru\&op=translate) sahifasi yordamida matnni rus yoki o'zbek tiliga tarjima qilib olishingiz mumkin.&#x20;

{% hint style="info" %}
Agar rus tilini bilsangiz, xato matnini rus tilga tarjima qiling. O'zbek tilidagi tarjimalar hali biroz tushunarsiz.
{% endhint %}

![Xatoning rus tilidagi tarjimasi](https://1283015017-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-MGbkqs1tROquIT6oqUs%2F-MN6IP9LWJtGJ36HcD1f%2F-MN6WUMJlEOmcASMDcxT%2Fimage.png?alt=media\&token=e65ecf60-bebd-4eeb-a9c4-f8b7ad5475d5)

![Xatoning o'zbek tilidagi tarjimasi](https://1283015017-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-MGbkqs1tROquIT6oqUs%2F-MN6IP9LWJtGJ36HcD1f%2F-MN6W_hZ_qfpVM8jsSo7%2Fimage.png?alt=media\&token=598b53de-808f-410f-9a04-8c9d0d6fe02f)

### EOL va EOF xatolik

EOL (End of Line - qator yakuni) xatoligi sintaks xatolikning bir turi bo'lib, odatda qator oxirida qo'shtirnoq (birtirnoq) ni yopish esdan chiqqanda yuzaga keladi.

```python
print("Hello World!
```

Natija: **`SyntaxError: EOL while scanning string literal`**

EOF (End of function - funktsiya yakuni) xatoligi esa funktsiya oxirida qavsni yopish esdan chiqqanda yuzaga keladi. &#x20;

```python
print("Hello World!"
```

Natija: **`SyntaxError: unexpected EOF while parsing`**

EOF xatoligining muammoli tarafi, Python aynan qaysi funktsiya yopilmay qolganini ko'rsata olmaydi, ya'ni kodni sinchiklab ko'zdan kechirib chiqish talab qilinadi.

## IndentationError - JOY TASHLASHDA XATOLIK

Python tilida qator boshidan yoki joy tashlab yozish muhim ahamiyatga ega. Qator boshidan asossiz joy qoldirish IndentationError ga olib keladi.&#x20;

Quyidagi kodga e'tibor bering, qator boshida 1 dona bo'sh joy qolgani uchunoq Spyder muhiti xatolikni aniqlab, qizil bilan belgilab qo'ydi.

![Asossiz bo'sh joy qoldirish ham xato](https://1283015017-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-MGbkqs1tROquIT6oqUs%2F-MN6IP9LWJtGJ36HcD1f%2F-MN6e3ewh_GD-rUVnjx5%2Fimage.png?alt=media\&token=61dff29e-9f39-4f15-8958-29ecc8dcfa24)

![IndentationError](https://1283015017-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-MGbkqs1tROquIT6oqUs%2F-MN6IP9LWJtGJ36HcD1f%2F-MN6ePDjpDvBQXM7MK5Y%2Fimage.png?alt=media\&token=77a0ac2a-a513-40f6-97ad-79df3df35361)

Ba'zi joylarda esa aksincha, bo'sh joy tashlab yozish talab qilinadi. Masalan, `for` tsiklida yoki `if-elif-else` shartlarining ichida va hokazo.

```python
print("O'ngacha sanaymiz")
for n in range(10):
print(n+1)
```

Natija: `IndentationError: expected an indented block`

```python
son = 50
if son>=0:
    print("Musbat son")
else:
print("Manfiy son")
```

Natija: `IndentationError: expected an indented block`

### QANCHA JOY TASHLAYMIZ?

Yuqoridagi misollarda IndentationError oldini olish uchun joy tashlash talab qilindi. Xo'sh, qancha joy tashlash kerak va qanday qilib?

Aslida, hech bo'lmaganda 1 harflik bo'sh joy qoldirish ham bizni IndentationError dan xalos qiladi. LEKIN, biz dastur davomida bir hil joy tashlashga odatlanishimiz kerak.&#x20;

Qoida sifatida kamida 4 ta harflik joy yoki 1 ta TAB (klaviaturadagi tab tugmasi) joy tashlashni odat qilishimiz kerak. Va eng muhimi ikkalasini aralashtirmasligimiz lozim. Ya'ni agar siz joy tashlash uchun Space (probel) ishlatsangiz, oxirigacha shunday qiling, agar Tab ishlatsangiz oxirigacha tab ishlating. Ikkalasini aralashtirmang!

![Joy tashlash uchun yoki 1 tab yoki 4 space ishlating](https://1283015017-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-MGbkqs1tROquIT6oqUs%2F-MN6IP9LWJtGJ36HcD1f%2F-MN6hZauiOId_z_XH8Mw%2Fimage.png?alt=media\&token=5405ded8-c5df-4459-b059-e9a297f365ea)

## RUN TIME ERROR - DASTURNI BAJARISHDA XATOLIK

**Run time error** — dastur bajarish jarayonida kelib chiqadi va dasturning ishlashini to'xtatadi. Sintaks xatolikdan farqli ravishda Python bunday xatolarni dasturni bajarishdan avval aniqlay olmaydi. Run time error ning bir necha turi bor. Keling, ulardan ba'zilari bilan tanishamiz.

### TypeError

Biror amalni (funktsiya, metod) noto'g'ri ma'lumot turi ustida bajarish.&#x20;

```python
son = input("Istalgan son kiriting: ")
print(f"{son} ning kvadrati {son**2} ga teng")
```

Natija: **`TypeError: unsupported operand type(s) for ** or pow(): 'str' and 'int'`**

Yuqoridagi kodda biz foydalanuvchi kiritgan qiymatni matndan songa o'tkazib olishni unutdik, natijada sonning kavdratini hisoblashda Python xato berdi.

### NameError

O'zgaruvchi, funktsiya, obyekt nomini noto'g'ri yozish natijasida kelib chiquvchi xatolik.

```python
prit("Hello World!")
```

Natija: `NameError: name 'prit' is not defined`

```python
mevalar = ['olma','uzum','nok','anor','anjir']
for meva in mvealar:
    print(meva)
```

Natija: `NameError: name 'mvealar' is not defined`

### ValueError

Funktsiyaga noto'g'ri qiymatni yuborish natijasidagi xatolik

```python
son = int(input("Istalgan son kiriting: "))
if son>=0:
    print("Musbat son")
else:
    print("Manfiy son")
```

![ValueError](https://1283015017-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-MGbkqs1tROquIT6oqUs%2F-MN6huQKAbuZZFJM2kdh%2F-MN6kzYnI1nnTmV2FtN_%2Fimage.png?alt=media\&token=a7844fb4-b483-452a-ad3a-0621bf3eb5cf)

Yuqoridagi dasturning 1-qatorida foydalanuvchidan istalgan son kiritishni so'rayabmiz, va foydalanuvchi kiritgan qiymatni `int` ya'ni butun songa o'tkazyabmiz. Kodning o'zida xato yo'q, lekin dastur bajarish jarayonida foydalanuvchi butun son emas, o'nlik son kiritgani uchun ValueError xatosi chiqdi. Sababi int() funktsiyasi faqatgina butun sonlar ko'rinishidagi matn bilan ishlaydi.

Dastur xato bermasligi uchun yoki `int()` funktsiyasini `float()` ga almashtrishimiz kerak, yoki foydalanuvchidan butun son kiritishni talab qilishimiz kerak.

### IndexError

Yangi dasturchilar yo'l qo'yadigan yana bir xato bu indeks xatolik. Ya'ni ro'yxat elementlariga murojat qilishda indeksni noto'g'ri kiritish.

```python
mevalar = ['olma','anor','uzum']
print(mevalar[3])
```

Natija: **`IndexError: list index out of range`**

Bizda mevalar degan ro'yxat bor va ro'yxatda uchta meva bor. Biz 3-elementni konsolga chiqarmoqchimiz va print(mevalar\[3]) deb yozdik va IndexError natijasini oldik. Sababi, dasturlashda indeks 0 dan boshlanadi va 3-elementga murojat qilish uchun 2-indeksni tanlaymiz. Demak, to'g'ri kod:

```python
mevalar = ['olma','anor','uzum']
print(mevalar[2])
```

Natija: `uzum`

### ZeroDivisionError

Dastur jarayonida 0 ga bo'lish yuzaga kelgandagi xatolik

```python
x, y = 50, 50
z = 250/(x-y)
```

Natija: `ZeroDivisionError: division by zero`

## MANTIQIY XATOLAR

Mantiqiy xatolar - dasturchi tomonidan yo'l qo'yilgan va kutilgan natijani berishda to'sqinlik qiluvchi xatolar. Bunday xatolar eng ko'p uchraydigan va aniqlash eng qiyin bo'lgan xatolar hisoblanadi. Aksar holatlarda Python mantiqiy xatolarni aniqlamaydi va dastur bajarilaveradi (lekin kutilgan natija chiqmaydi).&#x20;

Mantiqiy xatolar turli ko'rinishda bo'lishi mumkin, masalan sonlar bilan ishlashda:

```python
radius = 5
pi = 4.14
aylana_yuzi = pi*radius**2
print(aylana_yuzi)
```

Natija: `103.49999999999999`

Yuqoridagi kod bajarildi, va natija ham chiqdi. Lekin natija xato. Nima uchun? Sababi biz $$\pi=4.14$$ deb, xato yozib ketdik.

Yana bir misol ko'raylik:

```python
son = float(input("Istalgan son kiriting: "))
ildiz = son**1/2
print(f"{son} ning ildizi {ildiz} ga teng")
```

![Natija](https://1283015017-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-MGbkqs1tROquIT6oqUs%2F-MN6ve7EAO_ir3jftlmH%2F-MN701wXTmevN_Ey98UH%2Fimage.png?alt=media\&token=efc678ba-5db9-4865-a030-c7c68c64e850)

Yuqoridagi natijaga e'tibor bersangiz, 9 sonining ildizi 4.5 deb chiqdi. Sababi, 2-qatorda ildizni hisoblashda foydalanuvchi kiritgan son avval 1-darajaga oshirildi va undan keyin 2 ga bo'lindi. Kodni to'g'rilaymiz:

```python
son = float(input("Istalgan son kiriting: "))
ildiz = son**(1/2)
print(f"{son} ning ildizi {ildiz} ga teng")
```

![Natija](https://1283015017-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-MGbkqs1tROquIT6oqUs%2F-MN6ve7EAO_ir3jftlmH%2F-MN70bRD91k6nEB3xBUi%2Fimage.png?alt=media\&token=9256c983-a351-46a7-b577-61860ab5a8ed)

Noo'rin bo'sh joy qoldirish (yoki qoldirmaslik) ham mantiqiy xatoga olib kelishi mumkin:

```python
mevalar = ['olma','uzum','nok','anor','anjir']
for meva in mevalar:
    print(meva)
    print("Dastur tugadi")
```

![Natija](https://1283015017-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-MGbkqs1tROquIT6oqUs%2F-MN711S2_BZJWrZ9sTF2%2F-MN7VqRxHm7PBPLhXNWb%2Fimage.png?alt=media\&token=4b1809ec-4da8-4085-9e41-8504d798e181)

Yuqorida "Dastur tugadi" matni bir marta, dastur tugaganidan so'ng chiqishi kerak edi. Lekin o'ngga suriib qolgani uchun bir necha bor qaytarildi.&#x20;

Bundan boshqa ham mantiqiy xatoliklar juda ko'p uchraydi.&#x20;

Mantiqiy xatoliklar mutlaqo topilmasdan ham qolib ketishi, va dastur bozorga chiqqanidan so'ng aniqlanishi tabiiy hol. Shuning uchun ham aksar dasturlar tez-tez yangilanib turadi.

![](https://1283015017-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-MGbkqs1tROquIT6oqUs%2F-MN711S2_BZJWrZ9sTF2%2F-MN7Tct3drpUzN2KqcK5%2Fimage.png?alt=media\&token=aab599c0-9b5f-4491-8fe8-938117f10204)

Dastur jarayonida bundan boshqa xatoliklar ham ko'p uchraydi. Biz ulardan ba'zilari bilan tanishdik xolos. Keyingi darslarimizda Runtime xatoliklarni qanday qilib dastur davomida aniqlash, va dastur to'xtab qolishining oldini olishni o'rganamiz.

## AMALIYOT

Quyida Repl.it sahifasida bir nechta kodlar berilgan, kodlar avvalgi darsdagi uy vazifalaridan iborat. Kodlardagi xatolarni toping va to'g'rilang. Har bir dasturda bir nechta xatolar mavjud bo'lishi mumkin. Xatolarni topish uchun dasturlarni bir necha marta, turli qiymatlar bilan bajarib ko'ring.&#x20;

Kodlarni kompyuterda tekshirish uchun quyidagi faylni yuklab oling:

{% file src="<https://1283015017-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-MGbkqs1tROquIT6oqUs%2F-MN7wUTgE0lJ2KalTwRr%2F-MN7x-TZp3EBI9xgB9qW%2F12-dars-errors.zip?alt=media&token=a6047820-3f08-437a-8635-1f1e7af68736>" %}
12-dars savollar
{% endfile %}

{% embed url="<https://repl.it/@anvarbek/javoblar-12-dars-01>" %}

{% embed url="<https://repl.it/@anvarbek/javoblar-12-dars-02>" %}

{% embed url="<https://repl.it/@anvarbek/javbolar-12-dars-03>" %}

{% embed url="<https://repl.it/@anvarbek/javoblar-12-dars-04a>" %}

{% embed url="<https://repl.it/@anvarbek/javoblar-12-dars-04b>" %}

{% embed url="<https://repl.it/@anvarbek/javoblar-12-dars-05>" %}

## JAVOBLAR

{% file src="<https://1283015017-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-MGbkqs1tROquIT6oqUs%2F-MN3bNMGxI8LpxCi-Pf3%2F-MN3gkOcq5rPFTnUKMgB%2F11-dars-if-elif-else.zip?alt=media&token=fbb90b19-7c0a-4fcd-84d4-f12070f9c6b0>" %}
12-dars javoblari (11-dars bilan bir hil)
{% endfile %}


---

# Agent Instructions: Querying This Documentation

If you need additional information that is not directly available in this page, you can query the documentation dynamically by asking a question.

Perform an HTTP GET request on the current page URL with the `ask` query parameter:

```
GET https://python.sariq.dev/lirik-chekinish-1/12-xatolar.md?ask=<question>
```

The question should be specific, self-contained, and written in natural language.
The response will contain a direct answer to the question and relevant excerpts and sources from the documentation.

Use this mechanism when the answer is not explicitly present in the current page, you need clarification or additional context, or you want to retrieve related documentation sections.
