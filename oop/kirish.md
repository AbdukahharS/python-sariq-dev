# OOP NIMA?

<Embed url="https://www.youtube.com/watch?v=1CascMOFoi0&t=2s" />

## KIRISH

Dasturlashni o’rganar ekanmiz, albatta object oriented programming (OOP) ya’ni obyektga yo’naltiriglan dasturlash tushunchasiga kelamiz. Ko’pchilik uchun bu bosqich biroz tushunarsiz va murakkabdek tuyuladi. Aslida unday emas. Keling bugun object oriented programming va unga tegishli tamoyillar haqida gaplashamiz.

## KLASSIK YOHUD CHIZIQLI DASTURLASH

OOPni tushunish uchun avval klassik dasturlashni ko’raylik. Gap shundaki ilk kompyuterlar va dasturlar matematik muammolarni hal qilishga qaratilgan. Bunday dasturlar foydalanuvchidan biror ma’lumotlarni qabul qilib olgan, va qati’iy ketma-ketlik ya’ni tartibga amal qilgan holda turli arifmetik amallarni bajarib, dastur so’ngida foydalanuvchi kutgan natijani qaytargan. Shuning uchun ham bunday dasturlar chiziqli yoki tartibli dasturlar deb ataladi.

![Chiziqli dasturlash](../cirth-assets/f39b7a3a-a92f-44d9-9618-2a6064e0787d.png)

Siz ham dasturlashga ilk qadam qo’yganingizda mana shunday chiziqli dasturlarni yozishni o’rganishdan boshlaysiz.
Sizning dasturingiz bir nechta o’zgaruvchilar va funksiyalardan iborat bo’ladi.
Bu o’zgaruvchilar va funksiyalar ma’lum ketma-ketlikda bir biri bilan munosabatga kiradi va dastur yakunida siz kutgan natijani beradi.

![Chiziqli dastur tarkibi va algoritmi](../cirth-assets/698365c6-f8ec-4210-9ba7-35837c373a11.png)

Dastur kattalashgani sari o’zgaruvchilar va funksiyalar soni ortib boradi. Ular o’rtasidagi munosabatlar ham chigallashib, kodingiz murakkab va tushunishga qiyin bo’lib ketadi.
Dasturlash jarayonida bitta funksiyaga o’zgartirish kiritishingiz esa, unga bo’gliq boshqa funksiylaraning ishdan chiqishiga va dasturingiz xato natija berishiga olib kelishi ham mumkin.

![Chiziqli dastur murakkablashib ketishi mumkin](../cirth-assets/3da0d3b5-9721-465a-91ff-53afc4eae5ff.png)

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
Bir obyektga tegishli o’zgaruvchilar uning xususiyatlari, unga tegishli funksiyalar esa metodlari deb ataladi.

![OBYEKT](../cirth-assets/1ccc9d24-ec02-4f5f-9c5b-2ea3f930eaa2.png)

Keling misol tariqasida avtomobil degan obyektni ko’ramiz. Avtomobilning `modeli`, `rangi` va `narhi` uning xususiyatlari. Avtomobilga tegishli bo’lgan `start()`, `stop()` va `tezlashish()` kabi amallar esa uning metodlari deyiladi.

![AVTOMOBIL obyekti](../cirth-assets/3aa5d541-d868-4f74-ba62-0f787c3aae8f.png)

Agar real dasturdan misol keltiradigan bo’lsak, istalgan dastur ichidagi tugma bu obyekt. Uning shakli, rangi va matni esa xususiyatlari bo’ladi. Tugma ustida bajariladigan amallar tugmaning metodlari deyiladi. Misol uchun tugmani bosish, uzoq bosish, ustiga sichqonchani olib borish va hokazo.

![Dastur ichidagi Tugma ham aslida obyekt](../cirth-assets/1f43ba28-9f95-467a-956d-fd2f00bbfe0d.png)

Object oriented dasturlar on’lab balki yuzlab obyektlardan iborat bo’ladi va bunday dasturlar uchun dastur boshi yoki oxiri degan tushunchalar nisbiy bo’ladi.

Object oriented dasturlar bajarilishida qat’iy ketma-ketlikka amal qilmaydi. Foydalanuvchi istlagan obyektga murojat qilishi, uning ustida turli amallar bajarishi mumkin. O’z navbatida bitta obyektga murojat ortidan boshqa obyektlar ham faollashishi mumkin.

![Dasturlar o'nlab obyektlardan iborat bo'ladi](../cirth-assets/0ce4e167-1f4e-4355-a973-a341fbf02653.png)

Misol uchun, mobil ilovalarda obyektlar bu dastur ichidagi tugmalar, matnlar, rasmlar va boshqa elementlardir. Foydalanuvchi istalgan tugmani bosishi, istalgan matnni ajratib olishi va boshqa amallarni istalgan tartibda bajarishi mumkin. Bunda bitta tugma (ya’ni obyektni) bosish bulan boshqa obyekt (masalan rasm) o’zgarishi mumkin.

Zamonaviy kompyuter o’yinlari ham minglab obyektlardan iborat. Foydalanuvchi esa virtual o’yin olamida erkin harakat qilishi, istlagan tarafga yurishi, istalgan vaqtda turli obyektlar bilan turli amallar bajarishi mumkin.

## KLASS NIMA?

Object oriented programming haqida gaplashar ekanmiz uning fundamental tushunchalaridan biri - **klass** haqida gapirib o’tmaslikning iloji yo’q
.
Klass bu obyekt yaratish uchun shablon yoki qolipdir. Bitta klassdan biz istalgancha nusxa olishimiz va yangi obyektlar yaratishimiz mumkin. Demak obyekt bu biror klassning xususiy ko’rinishi.
Odatda klasslarning nomi o’zgarmas, undan yaratilgan obyektlar esa istalgancha nomlanishi mumkin.

![Klass va obyektlar](../cirth-assets/937d17b2-b586-4745-a56d-07e771ded40c.png)

Avval aytganimizdek, dasturimiz yuzlab obyektlardan iborat bo’lishi mumkin. Klasslar esa bizga obyektlarni yaratishni yengillashtiradi.

Bu xoh dastur interfeysidagi o’nlab turli hil tugmalar bo’lsin, yoki kompyuter o’yinidagi qahramonlar bo’lsin. Har bir tugma yoki o’yin qahramoni va uning harakatlarini qayta-qayta yozmasdan bir martta yaratilgan klassdan nusxa olib, o’nlab obyektlarni yaratishimiz mumkin.

![Yagona klassdan yaratilgan obyketlar turli ko'rinishda bo'lishi mumkin](../cirth-assets/8c5de5c5-3f69-44a4-b11a-6fb21a1ef563.png)

## OOP TAMOYILLARI

### INKAPSULYATSIYA

Biz object oriented dasturlash haqida gapira turib, ma’lum bir obyektga tegishli bo’lgan xususiyatlar va metodlarni bitta konteynerga joylaymiz dedik. Bu jarayon inkapsulyatsiya (ya’ni kapsulaga solish) deb ataladi. Inkapsulyatsiya bizga klasslar yaratishga va keyinchalik bu klasslardan boshqa obyektlarni yaratishga yordam beradi.

### ABSTRAKTSIYA

Abstraktsiya yordamida biz kodimizning ichki tuzilishini yashiramiz. Ya’ni, tashqaridan qaraganda obyektimiz 2 ta parameter va 2 ta metoddan iborat bo’lishi mumkin, lekin obyekt to’g’ri ishlashi uchun uning ichida o’nlab boshqa o’zgaruvchilar va funksiyalar yashirin bo’ladi.
Klassdan foydalanishda esa uning ichki tuzilishi va qanday ishlashini bilish talab qilinmaydi. Bu o’zimizga ham boshqa dasturchilarga ham bu klassdan foydalanishda qulayliklar yaratadi.

![Abstraktsiya](../cirth-assets/ccf944a0-2ab5-4918-a646-d85a8ceec124.png)

### VORISLIK

Dasturlash jarayonida biz bir klassdan boshqa klasslar yaratishimiz mumkin. Misol uchun bizda transport klassi bor, biz bu klassdan qo’shimcha Avtomobil, avtobus, kema, poyezd kabi klasslarni yaratishimiz mumkin.
Bunda bizning asl klassimiz ota yoki super klass deb ataladi, undan yaratilgan klasslar esa voris klasslar deyiladi.

![](../cirth-assets/a14bcfaa-e660-4291-b8e2-07e4c262b8ac.png)

:::tip
**Voris klasslar ota klassning ba’zi yoki barcha xususiyatlari va metodlariga ega bo’ladi.**
:::

POLIMORFIZM

Voris klass super klassdan o’zlashtirilgan metodning nomini saqlagan holda, uning ishlashini o’zgartirishiga **polimorfizm** deyiladi.

Keling bir misol ko’raylik. Biz kompyuter o’yini yaratish jarayonida o’yin Qahramon uchun super klass yaratamiz.
Qahramon bir nechta xususiyatlarga va metodlarga ega. Jumladan **`attack()`** ya’ni xujum qilish metodi, qahramonni xujum qilishga undaydi.
Endi biz bu superklassdan boshqa voris klasslarni yaratamiz.

![Superklass va voris klasslar](../cirth-assets/380c42ca-a9d3-478d-a8a9-e8b66a2f5fac.png)

1. Birinchi qahramonimiz Qilichboz va bu qahramon xujum qilganda qilich bilan xujum qiladi.
2. Ikkinchi qahramonimiz esa Jangchi, va u qurolsiz bo’lgani sababi qo’l va oyoqlari bilan xujum qiladi.
3. Uchunchi qahramonimiz pistolet bilan,
4. Oxrigisi esa kamon va yoylar bilan qurollangan.

To’rttala qahramonimiz ham superklassdan **`attack()`** metodini meros oladi, lekin bu metodni biz har bir qahramon uchun turli ko’rinishda yozishimiz va talqin qilishimiz mumkin. Bu esa o’z navbatida bizni turli qahramonlar va turli xujum turlari uchun alohida metodlar yozishdan qutqaradi.

Mana shular OOPning asosiy tamoyillari ekan.

### OOP AFZALLIKLARI VA KAMCHILIKLARI

Keling darsimiz yakunida OOPning afzalliklari va kamchiliklariga ham to’xtalib o’tsak.

**Afzalliklari**

* Parallel dasturlash – bir loyihaning turli qismlari bir vaqtda yaratilishi mumkin
* Vorislik tamoyili klasslardan qayta foydanalish imkonini beradi
* Polimorfizm tamoyili klasslarni moslashuvchan qiladi
* Klasslardan boshqa dastur va loyihalarda qayta-qayta foydalanish mumkin

**Kamchiliklari**

* Dasturlashga yangi qadam qo’yganlar uchun biroz tushunarsiz
* Har doim ham samarali emas
* Ba’zida dasturimizni haddan tashqari murakkablashtirib yuborishi mumkin

OOP bilan qisqacha tanishuvimiz shundan iborat edi. Endi esa Python OOP bilan tanishuvni boshlasak ham bo'ladi.