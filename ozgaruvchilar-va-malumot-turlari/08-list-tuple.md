# #08 RO'YXATLAR BILAN ISHLASH

{% embed url="<https://www.youtube.com/watch?v=019Dzhf0rB0>" %}

## RO'YXATNI TARTIBLASH

Aksar holatlarda ro'yxat ichidagi elementlarni alifbo ketma-ketligida tartiblash talab qilinishi mumkin. Buning uchun list uchun maxsus **`.sort()`** metodidan foydalanamiz.

```python
cars = ['bmw','mercedes benz', 'volvo', 'general motors', 'tesla', 'audi']
cars.sort()
print(cars)
```

Natija: `['audi', 'bmw', 'general motors', 'mercedes benz', 'tesla', 'volvo']`

Kurib turibsiz, yuqoridagi ro'yxatimiz alifbo bo'yicha tartiblandi.

{% hint style="danger" %}
**Diqqat!** Tartiblashda katta harflar kichik harflardan avval kelishini hisobga oling. Agar matndagi so'zlarning bosh harfi katta-kichik aralash yozilgan bo'lsa, ularni bir ko'rinishga keltirib olish maqsadga muvofiq bo'ladi.
{% endhint %}

```python
cars = ['Bmw','mercedes benz', 'volvo', 'gm', 'tesla', 'audi']
cars.sort()
print(cars)
```

Natija: `['Bmw', 'audi', 'gm', 'mercedes benz', 'tesla', 'volvo']`

Yuqoridagi misolda 'Bmw' elementi katta harf bilan boshlangani uchun ro'yxatning boshidan joy oldi.

Ro'yxatni teskari tartibda saqlash uchun `.sort()` metodi ichida `reverse=True` argumentini ham kiritamiz.&#x20;

```python
cars = ['bmw','mercedes benz', 'volvo', 'general motors', 'tesla', 'audi']
cars.sort(reverse=True)
print(cars)
```

Natija: `['volvo', 'tesla', 'mercedes benz', 'general motors', 'bmw', 'audi']`

**`.sort()`** metodi ro'yxatni tartiblaydi. Ba'zida asl ro'yxat ichidagi elementlarning ketma-ketligini buzmagan holda ro'yxatni tartiblash talab qilinishi mumkin. Buning uchun **`sorted()`** funktsiyasidan foydalanamiz:

```python
mehmonlar = ['Odil', 'Hamid', 'Temur', 'Avazbek', 'Farruh', 'Shamsiddin']
print("sorted() qaytargan ro'yxat:", sorted(mehmonlar))
print("Asl ro'yxat o'zgarmas qoldi:", mehmonlar)
```

Natija:

`sorted() qaytargan ro'yxat: ['Avazbek', 'Farruh', 'Hamid', 'Odil', 'Shamsiddin', 'Temur']`

`Asl ro'yxat o'zgarmas qoldi: ['Odil', 'Hamid', 'Temur', 'Avazbek', 'Farruh', 'Shamsiddin']`

**`sorted()`** funktsiyasi yordamida teskari tartiblash uchun ham **`reverse=True`** argumentini beramiz:

```python
print(sorted(mehmonlar, reverse=True))
```

Natija: `['Temur', 'Shamsiddin', 'Odil', 'Hamid', 'Farruh', 'Avazbek']`

Yuoqridagi ikki usul bilan sonli ro'yxatlarni ham tartiblashimiz mumkin:

```python
ages = [12, 98, 34, 65, 34, 76, 11]
ages.sort()
print(ages)
print(sorted(ages, reverse=True))
```

Natija:

`[11, 12, 34, 34, 65, 76, 98]`

`[98, 76, 65, 34, 34, 12, 11]`

## RO'YXATNI AYLANTIRISH

Ba'zida ro'yxatni aylantirish (boshini oxiriga, oxirini boshiga) talab qilinishi mumkin. Buning uchun **`.reverse()`** metodidan foydalanamiz.

```python
fruits = ['pear','banana','apple','watermelon','lemon']
fruits.reverse()
print(fruits)
```

Natija: `['lemon', 'watermelon', 'apple', 'banana', 'pear']`

Natija va asl ro'yxatni solishtiring.

## RO'YXATNING UZUNLIGINI BILISH

Ro'yxatning uzunligi, ya'ni uning ichidagi elementlar sonini aniqlash uchun **`len()`** funktsiyasidan foydalanamiz:

```python
fruits = ['pear','banana','apple','watermelon','lemon']
print("Elementlar soni:",len(fruits)) # len(fruits) ro'yxat uzunligini qaytaradi
```

Natija: `Elementlar soni: 5`

## `range()` FUNKTSIYASI

Bu funktsiya yordamida biz ma'lum oraliqdagi sonlar ketma-ketligini yaratishimiz mumkin. **`list()`** funktsiyasi yordamida esa bu oraliqni ro'yxat shaklida saqlab olamiz:

```python
sonlar = list(range(0,10)) # 
print(sonlar)
```

Natija: `[0, 1, 2, 3, 4, 5, 6, 7, 8, 9]`

Yuqoridagi misolda `range(0,10)` funktsiyasi `0` dan `9` gacha sonlar ketma-ketligini shakllantirdi, `list(range(0,9))` esa bu ketma-ketlikni ro'yxatga aylantirdi.

{% hint style="danger" %}
**Diqqat!** E'tibor qiling **`range()`** funktsiyasi ikkinchi indeksdan bitta avval to'xtaydi.
{% endhint %}

**`range()`** yordamida qadamni ham berishimiz mumkin:

```python
juft_sonlar = list(range(0,20,2)) # 0 dan 20 gacha 2 qadam bilan
toq_sonlar = list(range(1,20,2))  # 1 dan 20 gacha 2 qadam bilan
print("Juft sonlar: ", juft_sonlar)
print("Toq sonlar: ", toq_sonlar)
```

Natija:

`Juft sonlar: [0, 2, 4, 6, 8, 10, 12, 14, 16, 18]`&#x20;

`Toq sonlar: [1, 3, 5, 7, 9, 11, 13, 15, 17, 19]`

{% hint style="info" %}
Agar sonlar ketma-ketligi 0 dan boshlansa, `range()` funktsiyasida yakuniy indeksni ko'rsatish kifoya. Misol uchun `range(0,10)` emas `range(10)` deb yozsak ham bo'laveradi.
{% endhint %}

## SONLI RO'YXAT USTIDA SODDA AMALLAR

Pythonda ro'yxatlar ustida ba'zi sodda amallarni ham bajarish mumkin. Misol uchun ro'yxatdagi eng kichik sonni topish uchun **`min()`** funktsiyasidan, eng katta sonni topish uchun esa **`max()`** funktsiyasidan, sonlarning yig'indisini topish uchun esa **`sum()`** funktsyasidan foydalansak bo'ladi:

```python
narhlar = [12000, 22500, 23456, 9800, 5600, 9934, 32874]
arzon = min(narhlar)
qimmat = max(narhlar)
jami = sum(narhlar)
print("Eng arzon narh ", arzon, ". Eng qimmati ", qimmat, ". Jami: ", jami)
```

Natija: `Eng arzon narh 5600 . Eng qimmati 32874 . Jami: 116164`

## RO'YXATNI KESISH

Ba'zida ro'yxatning ma'lum bir bo'lagini ajratib olish talab qilinishi mumkin, deylik biz quyidagi cars degan ro'yxatdan birinchi 3 ta elementni ajratib olmoqchimiz, buning uchun biz boshlang'ich va oxirgi indekslarni beramiz:

```python
cars = ['bmw','mercedes benz', 'volvo', 'general motors', 'tesla', 'audi']
my_cars = cars[0:3] # 0-indeskdan boshlab 3 ta element ajratib olamiz
print(my_cars) 
```

Natija: `['bmw', 'mercedes benz', 'volvo']`

{% hint style="danger" %}
**Diqqat!** Python 2-indeksdan bitta avval to'xtaydi. Yuqoridagi misolda ham 0,1,2-elementlar ajratib olindi.
{% endhint %}

Bu usul bilan ro'yxatning istalgan joyidan bo'lishimiz mumkin:

```python
print(cars[2:5]) # 2-3-4-elementlarni ajratib olamiz (5 kirmaydi)
```

Natija: `['volvo', 'general motors', 'tesla']`

Agar boshlang'ich indeksni bermasangiz, Python avtomat ravishda `0` indeksdan boshlab kesadi. Agar 2-indeksni kiritmasangiz, ro'yxat oxirigacha kesadi:

```python
print(cars[:4]) # Ro'yxat boshidan 4-gacha kesadi (0,1,2,3)
print(cars[2:]) # 2-elementdan boshlab ro'yxat oxirigacha kesib oladi
```

Natija:

`['bmw', 'mercedes benz', 'volvo', 'general motors']`&#x20;

`['volvo', 'general motors', 'tesla', 'audi']`

## RO'YXATDAN NUSXA OLISH

Dastur davomida biror ro'yxatdan nusxa olish talab qilinishi mumkin. Buning uchun biz tenglik(`=`) belgisidan foydalansak bo'ladimi? Quyidagi misolga e'tibor bering:

```python
sonlar = [1, 2, 3, 4, 5] # donlar degan ro'yxat yaratamiz
sonlar2 = sonlar # sonlar2 degan ro'yxatni sonlar ga tenglaymiz
sonlar2.append(6) # sonlar2 ga 6 sonini qo'shamiz
sonlar2.append(7) # sonlar2 ga 7 sonini qo'shamiz
print("Bu sonlar ro'yxati:", sonlar)
print("Bu sonlar2 ro'yxati:", sonlar2)
```

Natija:

`Bu sonlar ro'yxati: [1, 2, 3, 4, 5, 6, 7]`&#x20;

`Bu sonlar2 ro'yxati: [1, 2, 3, 4, 5, 6, 7]`

Natija biz kutgandek chiqdimi? Yo'q. Biz 6 va 7 sonlarini `sonlar2` degan ro'yxatga qo'shgan edik, lekin bu ikki son `sonlar` degan asl ro'yxatga ham qo'shilib qoldi.&#x20;

Demak yuqorida biz `sonlar2=sonlar` deb yozgan komandamiz yangi ro'yxat yaratish o'rniga, ikkala o'zgaruvchini ham bitta ro'yxatga bog'lab (yo'naltirib) qo'ydi. Biz `sonlar` yoki `sonlar2` ustida bajargan amallarimiz aslida bitta ro'yxat ustida bajarilyapti.

![Ikki o'zgaruvchi, bir ro'yxat](https://1283015017-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-MGbkqs1tROquIT6oqUs%2F-MMJGzmHuPgjikKMOl0R%2F-MMJv_JeF1G7uIfp5RRc%2Fimage.png?alt=media\&token=6f5d1db7-57d6-4ef3-983d-5fe640b44435)

Unda, qanday qilib ro'yxatdan nusxa olamiz? Buning uchun yuoqirdagi ka'bi ro'yxatni kesish usulidan foydalanamiz. Faqatgina, kvadrat qavs ichida ikkala indeksni ham ko'rsatmasdan, bo'sh qoldiramiz:

```python
sonlar = [1, 2, 3, 4, 5] # donlar degan ro'yxat yaratamiz
sonlar2 = sonlar[:] # [:] ro'yxatni to'liq ko'chirib oladi
sonlar2.append(6) # sonlar2 ga 6 sonini qo'shamiz
sonlar2.append(7) # sonlar2 ga 7 sonini qo'shamiz
print("Bu sonlar ro'yxati:", sonlar)
print("Bu sonlar2 ro'yxati:", sonlar2)
```

Natija:

`Bu sonlar ro'yxati: [1, 2, 3, 4, 5]`&#x20;

`Bu sonlar2 ro'yxati: [1, 2, 3, 4, 5, 6, 7]`

## TUPLES - O'ZGARMAS RO'YXAT

Dastur yaratish davomida o'zgarmas ro'yxat tuzish talab qilinishi mumkin. Pythonda bunday ro'yxatlar **tuples** deb yuritiladi. Tuple ichidagi qiymatlarni bir marta, dastur boshida beriladi va so'ngra o'zgartirib bo'lmaydi. List dan farqli ravishda, Tuple e'lon qilishda kvadrat qavslar `[]` o'rniga oddiy qavslar `()` ishlatiladi:

```python
tomonlar = (20, 30, 55.2)
print(tomonlar)
```

Natija: `(20, 30, 55.2)`

Tuple ichidagi elementlarga huddi ro'yxat elementlariga murojat qilingani kabi murojat qilinaveradi:

```python
toys = ('bus','car','bear','dino','snake','lizard')
print(toys[0])
print(toys[-1])
print(toys[2:5])
```

Natija:

`bus`&#x20;

`lizard`&#x20;

`('bear', 'dino', 'snake')`

Keling Tuple ichidagi biror elementning qiymatini o'zgartirib ko'ramiz:

```python
toys = ('bus','car','bear','dino','snake','lizard')
toys[3] = 'dragon'
```

Natija: **`TypeError: 'tuple' object does not support item assignment`**

Demak yuqorida ko'rib turganingiz kabi, bu operatsiya xatolikka olib keldi. Shu kabi ro'yxatdan biror elementni o'chirish yoki yangi element qo'shish ham mumkin emas.

Agar Tuple ga o'zgartirish talab qilinsa, yagona yo'li o'zgarmas ro'yxatni `list()` funktsiyasi yordamida **List** (oddiy ro'yxat) ko'rinishiga keltirib olish, o'zgarishlarni bajarsih va qaytarib `tuple()` funktsiyasi yordamida o'zgarmas ro'yxatga o'tkazish mumkin:

```python
toys = ('bus','car','bear','dino','snake','lizard') # o'zgarmas ro'yxat
toys = list(toys) # o'zgarmas ro'yxatni oddiy ro'yxatga (List) aylantiramiz
# Ro'yxatga o'zgartirishlar kiritamiz
toys.append('dragon')
toys.remove('bus')
toys[1] = 'mcqueen'
toys = tuple(toys) # Ro'yxatni qaytadan o'zgarmas ro'yxatga (Tuple) aylantiramiz
print(toys)
```

Natija: `('car', 'mcqueen', 'dino', 'snake', 'lizard', 'dragon')`

## AMALIYOT

* O'zingizga ma'lum davlatlarning ro'yxatini tuzing va ro'yxatni konsolga chiqaring
* Ro'yxatning uzunligini konsolga chiqaring
* `sorted()` funktsiyasi yordamida ro'yxatni tartiblangan holda konsolga chiqaring
* `sorted()` yordamida ro'yxatni teskari tartibda konsolga chiqaring
* Asl ro'yxatni qaytadan konsolga chiqaring
* `reverse()` metodi yordamida ro'yxatni ortidan boshlab chiqaring
* `sort()` metodi yordamida ro'yxatni avval alifbo bo'yicha, keyin esa alifboga teskari tartibda konsolga chiqaring.
* `120` dan `1200` gacha bo'lgan juft sonlar ro'yxatini tuzing
* Ro'yxatdagi sonlar yig'indisini hisoblang va konsolga chiqaring
* Ro'yxatdagi eng katta va eng kichik son o'rtasidagi ayirmani hisoblang va konsolga chiqaring
* Ro'yxatdagi elementlar sonini hisoblang
* Ro'yxatning boshidan, o'rtasidan va oxiridan 20 ta qiymatni konsolga chiqaring
* `taomlar` degan ro'yxat yarating va ichiga istalgan 5ta taomni kiriting
* `nonushta` degan yangi ro'yxatga `taomlar`dan nusxa oling
* Yangi ro'yxatda faqat nonushtaga yeyiladigan taomlarni qoldiring, va qo'shimcha 2 ta taom qo'shing
* Ikkala ro'yxatni ham (`taomlar` va `nonushta`) konsolga chiqaring
* Yuqoridagi nonushta ro'yxatini o'zgarmas ro'yxatga aylantiring va `nonushta[0] = "qaymoq va non"` deb qiymat berib ko'ring.

## JAVOBLAR

{% embed url="<https://repl.it/@anvarbek/javoblar-08-dars#main.py>" %}

{% file src="<https://1283015017-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-MGbkqs1tROquIT6oqUs%2F-MMTQIUdUN_Mpbv0mYwi%2F-MMTSsaeS5qXDN6H6Cz7%2Fjavoblar-08-dars.zip?alt=media&token=0f0ca2e1-8d03-409d-b3ab-e9e85401100d>" %}
\#08-dars javoblari
{% endfile %}


---

# Agent Instructions: Querying This Documentation

If you need additional information that is not directly available in this page, you can query the documentation dynamically by asking a question.

Perform an HTTP GET request on the current page URL with the `ask` query parameter:

```
GET https://python.sariq.dev/ozgaruvchilar-va-malumot-turlari/08-list-tuple.md?ask=<question>
```

The question should be specific, self-contained, and written in natural language.
The response will contain a direct answer to the question and relevant excerpts and sources from the documentation.

Use this mechanism when the answer is not explicitly present in the current page, you need clarification or additional context, or you want to retrieve related documentation sections.
