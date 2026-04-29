# OOP NIMA?

{% embed url="<https://www.youtube.com/watch?v=1CascMOFoi0&t=2s>" %}

## KIRISH

Dasturlashni o’rganar ekanmiz, albatta object oriented programming (OOP) ya’ni obyektga yo’naltiriglan dasturlash tushunchasiga kelamiz. Ko’pchilik uchun bu bosqich biroz tushunarsiz va murakkabdek tuyuladi. Aslida unday emas. Keling bugun object oriented programming va unga tegishli tamoyillar haqida gaplashamiz.

## KLASSIK YOHUD CHIZIQLI DASTURLASH

OOPni tushunish uchun avval klassik dasturlashni ko’raylik. Gap shundaki ilk kompyuterlar va dasturlar matematik muammolarni hal qilishga qaratilgan. Bunday dasturlar foydalanuvchidan biror ma’lumotlarni qabul qilib olgan, va qati’iy ketma-ketlik ya’ni tartibga amal qilgan holda turli arifmetik amallarni bajarib, dastur so’ngida foydalanuvchi kutgan natijani qaytargan. Shuning uchun ham bunday dasturlar chiziqli yoki tartibli dasturlar deb ataladi.

![Chiziqli dasturlash](https://1283015017-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-MGbkqs1tROquIT6oqUs%2F-MRITtoECb6KqlwBUN_l%2F-MRIV7Nrlq81VbYXd_tL%2Fimage.png?alt=media\&token=69de7b1d-b8a7-4e04-bbbd-a2896ff1aac3)

Siz ham dasturlashga ilk qadam qo’yganingizda mana shunday chiziqli dasturlarni yozishni o’rganishdan boshlaysiz.
&#x20;Sizning dasturingiz bir nechta o’zgaruvchilar va funksiyalardan iborat bo’ladi.
&#x20;Bu o’zgaruvchilar va funksiyalar ma’lum ketma-ketlikda bir biri bilan munosabatga kiradi va dastur yakunida siz kutgan natijani beradi.

![Chiziqli dastur tarkibi va algoritmi](https://1283015017-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-MGbkqs1tROquIT6oqUs%2F-MRITtoECb6KqlwBUN_l%2F-MRIWkZKVTORbmQ-YFZr%2Fimage.png?alt=media\&token=7de462b9-29f3-4d1c-beea-2554e59291f7)

Dastur kattalashgani sari o’zgaruvchilar va funksiyalar soni ortib boradi. Ular o’rtasidagi munosabatlar ham chigallashib, kodingiz murakkab va tushunishga qiyin bo’lib ketadi.&#x20;
Dasturlash jarayonida bitta funksiyaga o’zgartirish kiritishingiz esa, unga bo’gliq boshqa funksiylaraning ishdan chiqishiga va dasturingiz xato natija berishiga olib kelishi ham mumkin.&#x20;

![Chiziqli dastur murakkablashib ketishi mumkin](https://1283015017-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-MGbkqs1tROquIT6oqUs%2F-MRITtoECb6KqlwBUN_l%2F-MRIXRFmyYWzfzz-QpF-%2Fimage.png?alt=media\&token=2b4b640a-3c1b-4986-bae5-9e3ef3b4dc7f)

Chiziqli dasturlarning afzalliklari
:

* Dasturlashni o’rganish uchun qulay
* Sodda va tushunarli kod
* Dastur algoritmini kuzatish oson
* Dastur xotirada kamroq joy egallaydi

Chiziqli dasturlarning kamchiliklari
:

* Murakkab dasturlarni chziqili usulda yozish qiyin (ilojsiz)
* Bir dastur uchun yozilgan koddan boshqa dasturda qayta foydalanib bo’lmaydi
* Dastur ichidagi ma’lumotlar (o’zgaruvchilar) barcha funksiyalar uchun ochiq
* ZAMONAVIY DASTURLAR CHIZIQLI EMAS

Vaqt o’tib dasturlarga qo’yilgan talablar murakkablashib borgani sababli, chiziqli dasturlash tamoyili zamon talabiga javob bermay qo’ydi va 1970 yillarda object oriented programming tamoyili olg’a surila boshlandi.

## OBYEKT NIMA?

Object oriented dasturlashda o’zaro bo’gliq bo’lgan o’zgaruvchilar va funksiyalar bitta konteynerga jamlanadi va bunday konteynerlar obyekt deb ataladi.
&#x20;Bir obyektga tegishli o’zgaruvchilar uning xususiyatlari, unga tegishli funksiyalar esa metodlari deb ataladi.

![OBYEKT](https://1283015017-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-MGbkqs1tROquIT6oqUs%2F-MRITtoECb6KqlwBUN_l%2F-MRJ_DHQpNHfixqyLlLH%2Fimage.png?alt=media\&token=5cb7aefd-ed27-49d7-a5a2-6e2da1b8570f)

Keling misol tariqasida avtomobil degan obyektni ko’ramiz. Avtomobilning `modeli`, `rangi` va `narhi` uning xususiyatlari. Avtomobilga tegishli bo’lgan `start()`, `stop()` va `tezlashish()` kabi amallar esa uning metodlari deyiladi.

![AVTOMOBIL obyekti](https://1283015017-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-MGbkqs1tROquIT6oqUs%2F-MRITtoECb6KqlwBUN_l%2F-MRJ_oBiAI9O6bQqZewJ%2Fimage.png?alt=media\&token=a28deb37-8e1b-4e51-8ac3-4c880aecb4c6)

Agar real dasturdan misol keltiradigan bo’lsak, istalgan dastur ichidagi tugma bu obyekt. Uning shakli, rangi va matni esa xususiyatlari bo’ladi. Tugma ustida bajariladigan amallar tugmaning metodlari deyiladi. Misol uchun tugmani bosish, uzoq bosish, ustiga sichqonchani olib borish va hokazo.

![Dastur ichidagi Tugma ham aslida obyekt](https://1283015017-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-MGbkqs1tROquIT6oqUs%2F-MRITtoECb6KqlwBUN_l%2F-MRJaArYI00jI9h3uB0c%2Fimage.png?alt=media\&token=1bd26994-5f5d-4605-9886-5ebf74660d48)

Object oriented dasturlar on’lab balki yuzlab obyektlardan iborat bo’ladi va bunday dasturlar uchun dastur boshi yoki oxiri degan tushunchalar nisbiy bo’ladi.
&#x20;

Object oriented dasturlar bajarilishida qat’iy ketma-ketlikka amal qilmaydi. Foydalanuvchi istlagan obyektga murojat qilishi, uning ustida turli amallar bajarishi mumkin. O’z navbatida bitta obyektga murojat ortidan boshqa obyektlar ham faollashishi mumkin.

![Dasturlar o'nlab obyektlardan iborat bo'ladi](https://1283015017-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-MGbkqs1tROquIT6oqUs%2F-MRITtoECb6KqlwBUN_l%2F-MRJa_JC5RZbgX6R21f0%2Fimage.png?alt=media\&token=d1835139-25b3-4f7b-bba5-2e2bfc87b318)

Misol uchun, mobil ilovalarda obyektlar bu dastur ichidagi tugmalar, matnlar, rasmlar va boshqa elementlardir. Foydalanuvchi istalgan tugmani bosishi, istalgan matnni ajratib olishi va boshqa amallarni istalgan tartibda bajarishi mumkin. Bunda bitta tugma (ya’ni obyektni) bosish bulan boshqa obyekt (masalan rasm) o’zgarishi mumkin.

Zamonaviy kompyuter o’yinlari ham minglab obyektlardan iborat. Foydalanuvchi esa virtual o’yin olamida erkin harakat qilishi, istlagan tarafga yurishi, istalgan vaqtda turli obyektlar bilan turli amallar bajarishi mumkin.&#x20;

## KLASS NIMA?

Object oriented programming haqida gaplashar ekanmiz uning fundamental tushunchalaridan biri - **klass** haqida gapirib o’tmaslikning iloji yo’q
.&#x20;
Klass bu obyekt yaratish uchun shablon yoki qolipdir. Bitta klassdan biz istalgancha nusxa olishimiz va yangi obyektlar yaratishimiz mumkin. Demak obyekt bu biror klassning xususiy ko’rinishi.&#x20;
Odatda klasslarning nomi o’zgarmas, undan yaratilgan obyektlar esa istalgancha nomlanishi mumkin.

![Klass va obyektlar](https://1283015017-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-MGbkqs1tROquIT6oqUs%2F-MRITtoECb6KqlwBUN_l%2F-MRJcIpcOyZcSr-NS6Sf%2Fimage.png?alt=media\&token=0a016be8-97c0-4ebd-b191-8ccfdb5543d8)

Avval aytganimizdek, dasturimiz yuzlab obyektlardan iborat bo’lishi mumkin. Klasslar esa bizga obyektlarni yaratishni yengillashtiradi.&#x20;

Bu xoh dastur interfeysidagi o’nlab turli hil tugmalar bo’lsin, yoki kompyuter o’yinidagi qahramonlar bo’lsin. Har bir tugma yoki o’yin qahramoni va uning harakatlarini qayta-qayta yozmasdan bir martta yaratilgan klassdan nusxa olib, o’nlab obyektlarni yaratishimiz mumkin.

![Yagona klassdan yaratilgan obyketlar turli ko'rinishda bo'lishi mumkin](https://1283015017-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-MGbkqs1tROquIT6oqUs%2F-MRITtoECb6KqlwBUN_l%2F-MRJcg5FNc2GcvV2ftCh%2Fimage.png?alt=media\&token=10a9fa25-9d25-47e4-93ac-1758e79723ec)

## OOP TAMOYILLARI

### INKAPSULYATSIYA

Biz object oriented dasturlash haqida gapira turib, ma’lum bir obyektga tegishli bo’lgan xususiyatlar va metodlarni bitta konteynerga joylaymiz dedik. Bu jarayon inkapsulyatsiya (ya’ni kapsulaga solish) deb ataladi. Inkapsulyatsiya bizga klasslar yaratishga va keyinchalik bu klasslardan boshqa obyektlarni yaratishga yordam beradi.

### ABSTRAKTSIYA

Abstraktsiya yordamida biz kodimizning ichki tuzilishini yashiramiz. Ya’ni, tashqaridan qaraganda obyektimiz 2 ta parameter va 2 ta metoddan iborat bo’lishi mumkin, lekin obyekt to’g’ri ishlashi uchun uning ichida o’nlab boshqa o’zgaruvchilar va funksiyalar yashirin bo’ladi.&#x20;
Klassdan foydalanishda esa uning ichki tuzilishi va qanday ishlashini bilish talab qilinmaydi. Bu o’zimizga ham boshqa dasturchilarga ham bu klassdan foydalanishda qulayliklar yaratadi.

![Abstraktsiya](https://1283015017-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-MGbkqs1tROquIT6oqUs%2F-MRITtoECb6KqlwBUN_l%2F-MRJe_OYlwJikGLVSVcP%2Fimage.png?alt=media\&token=dd56d888-2e77-4c71-a0fd-600d4fbd2596)

### VORISLIK

Dasturlash jarayonida biz bir klassdan boshqa klasslar yaratishimiz mumkin. Misol uchun bizda transport klassi bor, biz bu klassdan qo’shimcha Avtomobil, avtobus, kema, poyezd kabi klasslarni yaratishimiz mumkin.&#x20;
Bunda bizning asl klassimiz ota yoki super klass deb ataladi, undan yaratilgan klasslar esa voris klasslar deyiladi.
&#x20;

![](https://1283015017-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-MGbkqs1tROquIT6oqUs%2F-MRITtoECb6KqlwBUN_l%2F-MRJfM86QK5yWOZLGMj9%2Fimage.png?alt=media\&token=745495e7-61f1-4513-b74f-f4322c147fdd)

{% hint style="success" %}
**Voris klasslar ota klassning ba’zi yoki barcha xususiyatlari va metodlariga ega bo’ladi.**&#x20;
{% endhint %}

POLIMORFIZM

Voris klass super klassdan o’zlashtirilgan metodning nomini saqlagan holda, uning ishlashini o’zgartirishiga **polimorfizm** deyiladi.
&#x20;

Keling bir misol ko’raylik. Biz kompyuter o’yini yaratish jarayonida o’yin Qahramon uchun super klass yaratamiz.&#x20;
Qahramon bir nechta xususiyatlarga va metodlarga ega. Jumladan **`attack()`** ya’ni xujum qilish metodi, qahramonni xujum qilishga undaydi.
&#x20;Endi biz bu superklassdan boshqa voris klasslarni yaratamiz.&#x20;

![Superklass va voris klasslar](https://1283015017-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-MGbkqs1tROquIT6oqUs%2F-MRITtoECb6KqlwBUN_l%2F-MRJgD3d7pGWA2jZJcLZ%2Fimage.png?alt=media\&token=5340c09a-0961-49ee-9a78-f8a23207c671)

1. Birinchi qahramonimiz Qilichboz va bu qahramon xujum qilganda qilich bilan xujum qiladi.
2. Ikkinchi qahramonimiz esa Jangchi, va u qurolsiz bo’lgani sababi qo’l va oyoqlari bilan xujum qiladi.
3. Uchunchi qahramonimiz pistolet bilan,&#x20;
4. Oxrigisi esa kamon va yoylar bilan qurollangan.

To’rttala qahramonimiz ham superklassdan **`attack()`** metodini meros oladi, lekin bu metodni biz har bir qahramon uchun turli ko’rinishda yozishimiz va talqin qilishimiz mumkin. Bu esa o’z navbatida bizni turli qahramonlar va turli xujum turlari uchun alohida metodlar yozishdan qutqaradi.

Mana shular OOPning asosiy tamoyillari ekan.&#x20;

### OOP AFZALLIKLARI VA KAMCHILIKLARI

Keling darsimiz yakunida OOPning afzalliklari va kamchiliklariga ham to’xtalib o’tsak.

**Afzalliklari**

* Parallel dasturlash – bir loyihaning turli qismlari bir vaqtda yaratilishi mumkin
* Vorislik tamoyili klasslardan qayta foydanalish imkonini beradi
* Polimorfizm tamoyili klasslarni moslashuvchan qiladi
* Klasslardan boshqa dastur va loyihalarda qayta-qayta foydalanish mumkin&#x20;

**Kamchiliklari**

* Dasturlashga yangi qadam qo’yganlar uchun biroz tushunarsiz
  &#x20;
* Har doim ham samarali emas
* Ba’zida dasturimizni haddan tashqari murakkablashtirib yuborishi mumkin

OOP bilan qisqacha tanishuvimiz shundan iborat edi. Endi esa Python OOP bilan tanishuvni boshlasak ham bo'ladi.


---

# Agent Instructions: Querying This Documentation

If you need additional information that is not directly available in this page, you can query the documentation dynamically by asking a question.

Perform an HTTP GET request on the current page URL with the `ask` query parameter:

```
GET https://python.sariq.dev/oop/kirish.md?ask=<question>
```

The question should be specific, self-contained, and written in natural language.
The response will contain a direct answer to the question and relevant excerpts and sources from the documentation.

Use this mechanism when the answer is not explicitly present in the current page, you need clarification or additional context, or you want to retrieve related documentation sections.
