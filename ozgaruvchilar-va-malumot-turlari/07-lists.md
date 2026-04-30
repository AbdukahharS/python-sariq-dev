# #07 LIST (RO'YXAT)

{% embed url="<https://www.youtube.com/watch?v=92UuA1jneuQ>" %}

## LIST BILAN TANISHAMIZ

Avvalgi darsimizda biz o'zgaruvchi yaratish, va uning ichida biror qiymatni (matn yoki son) saqlashni o'rgandik. Bunda biz bitta o'zgaruvchiga bitta qiymat berdik xolos.&#x20;

Bugun o'rganadigan navbatdagi mal'umot turi **List** (**ro'yxat**) deb ataladi. Ro'yxat o'z nomi bilan, bitta o'zgaruvchida bir nechta qiymatlarni saqlash imkonini beradi. Bu qiymatlar List **elementlari** deyiladi. Ro'yxatda son, matn yoki aralash turdagi elementlarni saqlash mumkin.&#x20;

List quyidagicha yaratiladi:

```python
mevalar = ['olma', 'anjir', 'shaftoli', "o'rik"] # mevalar ro'yxati (matnlar)
narhlar = [12000, 18000, 10900, 22000] # narhlar ro'yxati (sonlar)
sonlar = ['bir', 'ikki', 3, 4, 5] # sonlar va matnlar aralash ro'yxat
ismlar = [] # bo'sh ro'yxat
```

{% hint style="success" %}
Ro'yxat saqlaydigan o'zgaruvchilarni nomlashda *-lar*  (ko'plik) qo'shimchasini qo'shish maqsadga muvofiq bo'ladi (inlgiz tilida *-s*).&#x20;

Misol uchun: `mevalar`, `uylar`, `cars`, `toys`, `books`&#x20;
{% endhint %}

## LIST ELEMENTLARI

Ro'yxatdagi har bir element tartib bilan joylashgani sababli, biz istalgan elementga uning tartib raqami (indeksi) bo'yicha murojat qilishimiz mumkin.&#x20;

{% hint style="danger" %}
Dasturlash olamida indeks `0` dan boshlanadi! Ya'ni Listning birinchi elementing tartib raqami (indeksi) `0` ga, ikkinchi elementning indeksi `1` ga teng va hokazo.
{% endhint %}

```python
mevalar = ['olma', 'anjir', 'shaftoli', "o'rik"] # mevalar ro'yxati (matnlar)
print("Birinchi meva: ", mevalar[0])
print("Ikkinchi meva: ", mevalar[1])
```

Natija:&#x20;

`Birinchi meva: olma`&#x20;

`Ikkinchi meva: anjir`

Agar list ichidagi elementlar matn ko'rinishid bo'lsa, ularga [string metodlarni](https://python.sariq.dev/ozgaruvchilar-va-malumot-turlari/05-string#string-metodlari) qo'llashimiz mumkin:

```python
mevalar = ['olma', 'anjir', 'shaftoli', "o'rik"] # mevalar ro'yxati (matnlar)
print("Birinchi meva: ", mevalar[0].title())
print("Ikkinchi meva: ", mevalar[1].upper())
```

Natija:

`Birinchi meva: Olma`&#x20;

`Ikkinchi meva: ANJIR`

List elementlari ustida arifmetik amallar bajarish:

```python
narhlar = [12000, 18000, 10900, 22000]
print(narhlar[2] + narhlar[3])
```

Natija: `32900`

Pythonda Listning eng oxirgi elementiga `-1` indeksi orqali ham murojat qilish mumkin. Bu usul Listning uzunligini bilmaganda juda asqotadi.

```python
car_models = ['Toyota', 'GM', 'Volvo', 'BMW', 'Hyundai', 'Kia', 'Volkswagen']
print(car_models[-1]) # Listning eng oxirgi elementiga -1 bilan murojat qilamiz 
```

Natija: `Volkswagen`

## ELEMENTLARNI QO'SHISH, O'CHIRISH VA O'ZGARTIRISH

Dastur davomida listning tarkibi o'zgarishi, yangi elementlar qo'shilishi, ba'zi elementlar o'chirilishi tabiiy hol. Misol uchun "Bozorlik ro'yxati" degan dasturni tasavvur qilaylik, foydalanuvchi ro'yxatga yangi mahsulotlar qo'shishi, sotib olganlarini esa o'chrishi mumkin.&#x20;

### &#x20;Elementni o'zgartirish

Ro'yxatdagi biror elementning qiymatini o'zgartirish uchun, o'sha elementga indeksi bo'yicha murojat qilamiz va yangi qiymat yuklaymiz

```python
narhlar = [12000, 18000, 10900, 22000]
narhlar[0] = 13000 # 1-qiymatni 13000 ga o'zgartiramiz
narhlar[2] = 11000 # 3-qiymatni 11000 ga o'zgartiramiz
narhlar[3] = narhlar[3]+2000 # 4-qiymatga 2000 qo'shamiz
print(narhlar)
```

Natija: `[13000, 18000, 11000, 24000]`

### Yangi element qo'shish

#### `.append()` metodi

Ro'yxatga yangi element qo'shishning oson usuli bu **`.append()`** metodi yordamida ro'yxatning **oxiriga** qiymat qo'shish:

```python
mevalar = ['olma', 'anjir', 'shaftoli', "o'rik"]
mevalar.append("tarvuz") # mevalar ga tarvuz qo'shamiz
print(mevalar)
```

Natija: `['olma', 'anjir', 'shaftoli', "o'rik", 'tarvuz']`

**`.append()`** metodi bo'sh ro'yxatni to'ldrisihda juda qulay usul. Odatda dastur boshida bo'sh ro'yxat yaratilib, dastur davomida ro'yxat foydalanuvchi tomonidan to'ldirib borilishi odatiy hol.

```python
cars = [] # bo'sh ro'yxat yaratamiz
cars.append('Lacetti') # ro'yxatga Lacetti mashinasini qo'shamiz
cars.append('Nexia 3') # ro'yxatga Nexia 3 mashinasini qo'shamiz
cars.append('Cobalt')  # ro'yxatga Cobalt  mashinasini qo'shamiz
print(cars)
```

Natija: `['Lacetti', 'Nexia 3', 'Cobalt']`

#### `.insert()` metodi

Ro'yxatning istalgan joyiga yangi element qo'shish uchun **`.insert()`** metodidan foydalanamiz. `.insert()` metodi ichida yangi elementning indeksi va qiymati beriladi:

```python
cars = ['Lacetti', 'Nexia 3', 'Cobalt']
cars.insert(0, 'Malibu') # 1-o'ringa yangi qiymat qo'shamiz
print(cars)
```

Natija: `['Malibu', 'Lacetti', 'Nexia 3', 'Cobalt']`

```python
cars.insert(2, 'Damas') # 3-o'ringa yangi qiymat qo'shamiz
print(cars)
```

Natija: `['Malibu', 'Lacetti', 'Damas', 'Nexia 3', 'Cobalt']`

### Elementni o'chirish

Ro'yxatdan biror elementni olib tashlash uchun uning indeksini yoki qiymatini bilishimiz lozim.

Inedks yordamida olib tashlash uchun **`del`** operatoridan foydalanamiz:

```python
mevalar = ['olma', 'anjir', 'shaftoli', "o'rik", 'anor']
del mevalar[1] # 2-element (anjir) ni o'chirib tashlaymiz
print(mevalar)
```

Natija: `['olma', 'shaftoli', "o'rik", 'anor']`

Element qiymati bo'yichi o'chirish uchun esa **`.remove(qiymat)`** metodidan foydalanamiz. Buning uchun qavs ichida o'chirib tashlash kerak bo'lgan qiymatni yozamiz

```python
mevalar = ['olma', 'anjir', 'shaftoli', "o'rik", 'anor']
mevalar.remove('shaftoli') # Ro'yxatdan shaftolini o'chirdik
print(mevalar)
```

Natija: `['olma', 'anjir', "o'rik", 'anor']`

{% hint style="info" %}
**`.remove(qiymat)`** metodi ro'yxatda uchragan birinchi mos keluvchi qiymatni o'chiradi. Agar ro'yxatning ichida 2 va undan ko'p bir hil qiymatli elementlar bo'lsa, ulardan eng birinchisi o'chadi.
{% endhint %}

```python
hayvonlar = ['it', 'mushuk', 'sigir', 'qo\'y', 'quyon', 'mushuk']
hayvonlar.remove("mushuk") # Ro'yxatda 2 ta mushuk bor, ulardan birinchisi o'chadi
print(hayvonlar)
```

Natija: `['it', 'sigir', "qo'y", 'quyon', 'mushuk']`

### Elementni sug'urib olish

Ba'zida biror elementni butunlay o'chirib tashlash emas, balki uni ro'yxatdan sug'urib olish va undan foydalanish talab qilinishi mumkin. Buning uchun Pythonda **`.pop(indeks)`** metodidan foydalanmiz.

```python
bozorlik = ["yog'", 'un', 'piyoz', 'banan', "go'sht"]
mahsulot = bozorlik.pop(3) # Ro'yxatdan banan ni sug'urib olamiz
print("Men " + mahsulot + " sotib oldim")
print("Olinmagan mahsulotlar: ", bozorlik)
```

Natija:

`Men banan sotib oldim`&#x20;

`Olinmagan mahsulotlar: ["yog'", 'un', 'piyoz', "go'sht"]`

{% hint style="info" %}
Agar **`.pop()`** metodida indeks berilmasa, ro'yxatdan o'xirgi qiymat sug'urib olinadi.
{% endhint %}

## AMALIYOT

Quyidagi mashqlarni bajaring:

* `ismlar` degan ro'yxat yarating va kamida 3 ta yaqin do'stingizning ismini kiriting
* Ro'yxatdagi har bir do'stingizga qisqa xabar yozib konsolga chiqaring:&#x20;

![](https://1283015017-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-MGbkqs1tROquIT6oqUs%2F-MLvZJbRru8b9RC9s6ag%2F-MLvbRkA4uEAqqhKk6Yi%2Fimage.png?alt=media\&token=a768a42e-2516-4bbc-83ad-63d012758b25)

* `sonlar` deb nomlangan ro'yxat yarating va ichiga turli sonlarni yuklang (musbat, manfiy, butun, o'nlik).&#x20;
* Yuqoridagi ro'yxatdagi sonlar ustida turli arifmetik amallar bajarib ko'ring. Ro'yxatdagi ba'zi sonlarning qiymatini o'zgartiring, ba'zilarini esa almashtiring.&#x20;
* `t_shaxslar`va `z_shaxslar` degan 2 ta ro'yxat yarating va biriga o'zingiz eng ko'p hurmat qilgan tarixiy shaxslarning, ikkinchisiga esa zamonamizdagi tirik bo'lgan shaxslarning ismini kiriting.&#x20;
* Yuqoridagi ro'yxatlarning har biridan bittadan qiymatni sug'urib olib (**`.pop()`**), quyidagi ko'rinishda chiqaring:

![](https://1283015017-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-MGbkqs1tROquIT6oqUs%2F-MLvdTf93oJb9hVewsv7%2F-MLyyn0plvxsTJKVHnxQ%2Fimage.png?alt=media\&token=76b9a4e8-14fe-4d66-bde4-72464e6edbad)

* `friends`nomli bo'sh ro'yxat tuzing va unga `.append()` yordamida 5-6 ta mehmonga chaqirmoqchi bo'lgan do'stlaringizni kiriting.&#x20;
* Yuqoridagi ro'yxatdan mehmonga kela olmaydigan odamlarni `.remove()` metodi yordamida o'chrib tashlang.&#x20;
* Ro'yxatning oxiriga, boshiga va o'rtasiga yangi ismlar qo'shing.
* Yangi `mehmonlar`deb nomlangan bo'sh ro'yxat yarating. `.pop()` va `.append()` metodlari yordamida mehmonga kelgan do'stlaringizning ismini friends ro'yxatidan sug'urib olib, mehmonlar ro'yxatiga qo'shing.

## JAVOBLAR

{% embed url="<https://repl.it/@anvarbek/javoblar-07-dars-lists#main.py>" %}

{% file src="<https://1283015017-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-MGbkqs1tROquIT6oqUs%2F-MMTQIUdUN_Mpbv0mYwi%2F-MMTSOjDtnV5aXBcSP_g%2Fjavoblar-07-dars.zip?alt=media&token=6bfe3c26-11ad-4c94-bb53-62877a1d04b0>" %}
\#07-dars javoblari
{% endfile %}

