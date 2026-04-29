# #21 FUNKSIYA VA RO'YXAT

{% embed url="<https://www.youtube.com/watch?v=vNeZD2LTI94>" %}

## FUNKSIYAGA RO'YXAT UZATISH

Biz avvalgi darslarimizda funksiyaga parametr sifatida yagona qiymat berayotgan edik. Aslida, bu bilan cheklanmasdan, funksiyaga ro'yxat (list) ham berishimiz mumkin. Bunda, funksiya ro'yxat qiymatlariga to'g'ridan-to'g'ri murojat qila oladi.

Keling talabalarni baholaydigan funksiya yozamiz. Funksiyamiz talabalar ro'yxatini qabul qilib oladi, ro'yxatdan har bir talabani sug'urib olib (`.pop()`), bahosini kiritishni so'raydi. Talaba ismi va bahosini lug'atga joylab, yakuniy lug'atni foydalanuvchiga qaytaradi.

```python
def bahola(ismlar):
    baholar = {}
    while ismlar:
        ism = ismlar.pop()
        baho = input(f"Talaba {ism.title()}ning bahosini kiriting: ")
        baholar[ism]=baho
    return baholar

talabalar = ['ali', 'vali', 'hasan', 'husan']
baholar = bahola(talabalar)
print(baholar)
```

&#x20;

![Natija](https://1283015017-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-MGbkqs1tROquIT6oqUs%2F-MP8EGli8doB3A3zBciJ%2F-MP8VUSLldLwJVsvoVHI%2Fimage.png?alt=media\&token=ee3ef5d5-88cf-4d11-9e71-97e9669467c5)

## RO'YXATGA O'ZGARTIRISH KIRITISH

Funksiyaga ro'yxat uzatganimizda, funksiya ro'yxat elementlariga to'g'ridan-to'g'ri murojat qila oladi. Ro'yxatga funksiya ichida kiritilgan o'zgartirishlar asl ro'yxatga ham ta'sir qiladi. Avvalgi misolimizga qaytaylik:

```python
talabalar = ['ali', 'vali', 'hasan', 'husan']
baholar = bahola(talabalar)
print(talabalar)
```

Natija: `[]`

Yuqoridagi funksiya unga uzatilgan ro'yxat ichidagi talabalarning ismini `.pop()` yordamida sug'urib olgani uchun bizning asl ro'yxatimiz ham bo'shab qoldi. E'tibor bering, funksiya tashqarisidagi va ichidagi ro'yxatlar ikki hil nomlangan bo'lsada (`talabalar` va `ismlar`), ikkalasi ham xotiradagi bitta ro'yxatga bog'langani sabab ulardan biriga o'zgartirish kiritilishi bilan, ikkinchisi ham o'zgaradi.&#x20;

![Ikki o'zgaruvchi ham bitta ro'yxatga bog'langan](https://1283015017-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-MGbkqs1tROquIT6oqUs%2F-MP8EGli8doB3A3zBciJ%2F-MP8WrcRbEHkTZzbTVxR%2Fimage.png?alt=media\&token=3087463f-98b5-4c1f-b011-af040317ab9f)

## ASL RO'YXATGA O'ZGARTIRISH KIRITISHNING OLDINI OLISH&#x20;

Agar funksiya asl ro'yxatga o'zgartirish kiritishini istamasangiz, funksiyaga ro'yxatning o'zini emas, uning nusxasini uzatish mumkin. Buning uchun funksiya parametrini `royxat_nomi[:]` ko'rinishida yozish kifoya. Bunda `[:]` operatori ro'yxatdan nusxa olishni bildiradi:

```python
talabalar = ['ali', 'vali', 'hasan', 'husan']
baholar = bahola(talabalar[:])
print(talabalar)
```

Natija: `['ali', 'vali', 'hasan', 'husan']`

## AMALIYOT

* Matnlardan iborat ro'yxat qabul qilib, ro'yxatdagi har bir matnning birinchi harfini katta harfga o'zgatiruvchi funksiya yozing.&#x20;

```python
ismlar = ['ali', 'vali', 'hasan', 'husan']
katta_harf(ismlar)
print(ismlar)
```

Kutilgan natija: `['Ali', 'Vali', 'Hasan', 'Husan']`

* Yuoqirdagi funksiyani asl ro'yxatni o'zgartirmaydigan va yangi ro'yxat qaytaradigan qilib o'zgartiring

```python
ismlar = ['ali', 'vali', 'hasan', 'husan']
yangi_ismlar = katta_harf(ismlar)
print(ismlar)
print(yangi_ismlar)
```

Kutilgan natija:&#x20;

`['ali', 'vali', 'hasan', 'husan']`&#x20;

`['Ali', 'Vali', 'Hasan', 'Husan']`

* Darsimiz davomida yozgan bahola funksiyasini `.pop()` metodidan foydalanmasdan va asl ro'yxatga o'zgartirish kiritmasdan faqat lug'at qaytaradigan qilib yozing.

## JAVOBLAR

### GitHub

{% embed url="<https://github.com/anvarnarz/python-darslar>" %}

### Repl.it

{% embed url="<https://repl.it/@anvarbek/javoblar-21-01#main.py>" %}

{% embed url="<https://repl.it/@anvarbek/javoblar-21-02#main.py>" %}

{% embed url="<https://repl.it/@anvarbek/javoblar-21-03#main.py>" %}


---

# Agent Instructions: Querying This Documentation

If you need additional information that is not directly available in this page, you can query the documentation dynamically by asking a question.

Perform an HTTP GET request on the current page URL with the `ask` query parameter:

```
GET https://python.sariq.dev/function/21-funksiya-va-royxat.md?ask=<question>
```

The question should be specific, self-contained, and written in natural language.
The response will contain a direct answer to the question and relevant excerpts and sources from the documentation.

Use this mechanism when the answer is not explicitly present in the current page, you need clarification or additional context, or you want to retrieve related documentation sections.
