# #04 O'ZGARUVCHILAR

{% embed url="<https://www.youtube.com/watch?v=4-Sj_owtx3Q>" %}

## O'ZGARUVCHI (VARIABLE)

**O'zgaruvchi** —kompyuter xotirasida ma'lum bir qiymatni saqlash uchun ajratilgan joy. Soddaroq qilib tushuntirsak, o'zgaruvchini quti, quti ichidagi narsani esa qiymat deb tasavvur qilish mumkin. Pythonda qiymatlar son, matn, ro'yxat va hokazo ko'rinishida bo'lishi mumkin.

![O'zgaruvchilarni kerakli buyumlar (ma'lumotlat) saqlanadigan, nomlangan qutilarga o'xshatish mumkin](https://1283015017-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-MGbkqs1tROquIT6oqUs%2F-MLgatxylpGtKv0LiiV1%2F-MLgfAikZVcuHp-u5tHP%2FPic-of-labeled-boxes.jpg?alt=media\&token=4bdf283d-c483-4158-8ce3-90527594f363)

Quyidagi misolga e'tibor bering, biz 2 ta o'zgaruvchi yaratdik (`ism` va `yosh`) va ularga qiymatlar yukladik (Pythonda boshqa tillardagi ka'bi o'zgaruvchilarni avvaldan e'lon qilish yo'q):

```python
ism = "Abdulloh"
yosh = 25
print(ism)
print(yosh)
```

Natija:

`Abdulloh`

`25`

O'zgaruvchi (variable) bunday deyilishiga sabab, uning qiymati istalgan vaqt o'zgartirilishi mumkin:

```python
ism = "Abdulloh"
print(ism)
ism="Muhammad"
print(ism)
```

Natija:

`Abdulloh`

`Muhammad`

Yuqoridagi misolda `ism` nomli o'zgaruvchiga avval `Abdulloh` keyin esa `Muhammad` qiymatlarini berdik.

## O'ZGARUVCHILARNI NOMLASH

{% hint style="danger" %}
O'zgaruvchilarga nom berishda quyidagi qoidalarga amal qiling:

* O'zgaruvchi nomi harf yoki pastki chiziq (`_`) bilan boshlanishi kerak
* O'zgaruvchi nomi raqam bilan boshlanishi mumkin emas
* O'zgaruvchi nomida faqatgina lotin alifbosi harflari (`A-z`), raqamlar (`0-9`) va pastki chiziq (`_`) qatnashishi mumkin
* O'zgaruvchi nomida bo'shliq (пробел) bo'lishi mumkin emas
* O'zgaruvchi nomida katta-kichik harflar turlicha talqin qilinadi (`ism`, `ISM`, va `Ism` uchta turli o'zgaruvchi)
  {% endhint %}

Qo'shimcha qoida sifatida:&#x20;

* O'zgaruvchi nomini kichik harflar bilan yozing.&#x20;
* O'zgaruvchi nomida 2 va undan ortiq so'z qatnashsa ularning orasini pastki chiziq (\_) bilan ajrating (`ism_sharif="Anvar Narzullaev"`)
* O'zgaruvchiga tushunarli nom bering (`y=20` emas `yosh=20`, `d="Korea"` emas `davlat = "Korea"` va hokazo)
* Shuningdek o'zgaruvchilarga Pythonda ishlatiladigan funktsiyalar va maxsus kalit so'zlarning (keywords) nomini bermang. Kalit so'zlar ro'yhatini ko'rish uchun Spyder konsolida avval `help()` deb yozing va Enter tugmasini bosing. Keyin esa `keywords` deb kiritib, yana Enter bosing. Marhamat, ekraningizda Pythondagi maxsus kalit so'zlar ro'yhatini ko'ryapsiz:

![Bu so'zlardan o'zgaruvchilarni nomlashda foydalanmang](https://1283015017-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-MGbkqs1tROquIT6oqUs%2F-MLVzx_XI1kJZ-26z7qY%2F-MLW-W018dbAzZRednoA%2Fimage.png?alt=media\&token=d10d36e9-a759-4a23-b149-0c4fa791b405)

## AMALIYOT

Quyidagi mashqlarni bajaring:

* `"Hello World!"` matnini yangi o'zgaruvchiga yuklang va `print()` yordamida konsolga chiqaring
* `xabar` deb nomlangan o'zgaruvchiga biror matn yuklang va konsolga chiqaring, keyin esa o'zgaruvchiga yangi qiymat berib uni ham konsolga chiqaring.
* `class` den nomlangan o'zgaruvchi yarating, unga biror qiymat bering va konsolga chiqaring (siz kutgan natija chiqdimi?)
* Quyidagi kodni bajaring:

```python
radius = 5
pi = 3.14159
aylana_yuzi = pi * radius**2
print("Radiusi" , radius, "ga teng aylananing yuzi=", aylana_yuzi)
```

## JAVOBLAR

{% embed url="<https://repl.it/@anvarbek/javoblar-04-dars#main.py>" %}

{% file src="<https://1283015017-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-MGbkqs1tROquIT6oqUs%2F-MLXApyXUq0jDUHl-zUt%2F-MLXBcizC30Pmh8NBXjT%2Fjavoblar-04-dars.zip?alt=media&token=93903759-bad4-45d0-bac9-3458a811e13b>" %}
04-dars javoblari
{% endfile %}


---

# Agent Instructions: Querying This Documentation

If you need additional information that is not directly available in this page, you can query the documentation dynamically by asking a question.

Perform an HTTP GET request on the current page URL with the `ask` query parameter:

```
GET https://python.sariq.dev/ozgaruvchilar-va-malumot-turlari/04-variables.md?ask=<question>
```

The question should be specific, self-contained, and written in natural language.
The response will contain a direct answer to the question and relevant excerpts and sources from the documentation.

Use this mechanism when the answer is not explicitly present in the current page, you need clarification or additional context, or you want to retrieve related documentation sections.
