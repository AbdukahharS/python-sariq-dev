# #06 SONLAR

Dasturlash davomida turli sonlar bilan ishlash tabiiy hol. Pythonda sonlarning bir necha turlari bor. Keling ular bilan yaqindan tanishaylik.

<Embed url="https://www.youtube.com/watch?v=_1eGzQpAtC8" />

## INTEGERS — BUTUN SONLAR

Butun sonlarni ham o'zgaruvchida saqlash, ularning ustida qo'shish (`+`), ayirish (`-`), ko'paytirish(`*`), bo'lish (`/`) kabi [arifmetik amalarni ](https://python.sariq.dev/ilk-qadamlar/03-print#arifmetik-amallar)bajarish mumkin:

```python
a = 20  # Sonlar musbat yoko
b = -30 # manfiy bo'lishi mumkin
c = a + b
print(c)
```

Natija: `-10`

:::info
Python - operatorlar orasidagi bo'shliqlarni inobatga olmaydi. O'qishga qulay bo'lishi uchun yuqoridagi kabi (bo'shliqlar bilan) yozishingiz mumkin.
:::

```python
# Kvadratning yuzini hisoblaymiz
kvdrt_tmni = 20 # Kavdratning tomoni 20 ga teng
kvdrt_yuzi = kvdrt_tmni**2 # Kvadrat yuzini hisoblaymiz
print(kvdrt_yuzi)
```

Natija: `400`

## FLOATS — O'NLIK SONLAR

Pythonda o'nlik sonlar **floating point numbers** yoki qisqa qilib **floats** deyiladi. "*Floating point numbers*" atamasini o'zbek tiliga "*suzuvchi nuqtali sonlar*" deb tarjima qilish mumkin. Ingliz tilida o'nlik sonlarni yozishda vergul (`,`) emas nuqta (`.`) belgisi ishlatiladi, va bu nuqta sonning katta kichikligiga qarab joyi o'zgargani uchun *"floating"* *(suzuvchi)* deyiladi.

```python
pi = 3.14159 # o'nlik son (float)
radius = 10  # butun son (integer)
diametr = 2*radius
print("Aylana uzunligi ", pi*diametr, " ga teng.")
```

Natija: `Aylana uzunligi 4.712384999999999 ga teng.`

## BUTUN SONDAN O'NLIK SONGA

Avval aytganimizdek ikki butun sonni bo'lish (`/`) natijasida o'nlik son hosil bo'ladi (natija butun bo'lsa ham).

```python
a = -20
b = 40
c = b/a
print(c) # natija o'nlik son bo'ladi
```

Natija: `-2.0`

Shuningdek butun va o'nlik sonlar o'rtasidagi har qanday arifmetik amallarning natijasi ham o'nlik son bo'ladi.

```python
a = 2
b = 3.0
# Quyidagi arifmetik amallarning natijasi o'nlik son hosil qiladi
print(a+b) 
print(a*b)
print(a**b)
print(2*(a+b))
```

Natijalar:

`2.0`

`5.0`

`6.0`

`8.0`

`10.0`

## UZUN SONLARNI KIRITISH

Uzun sonlarni kiritishda, qulaylik uchun, raqamlarni pastki chiziq (`_`) yordamida guruhlash mumkin. Python - son tarkibidagi pastki chiziqlarni (`_`) inobatga olmasdan, uzun sonligicha qabul qiladi.

```python
aholi_soni = 7_594_000_000 # o'zmizga qulay bo'lishi uchun shinday yozdik
print("Yer kurrasida", aholi_soni, " ga yaqin odam yashaydi")
```

Natija: `Yer kurrasida 7594000000 ga yaqin odam yashaydi`

## KONSTANTA

Aksar dasturlash tillarida konstant qiymatlar tushunchasi bor. Konstantlar o'zgarmas bo'ladi (misol uchun$$\pi$$ ning qiymati konstant, o'zgarmas qiymat). Pythonda konstant tushunchasi yo'q, shuning uchun dasturchilar bunday o'zgaruvchilarning nomini katta harflar bilan yozadilar (*ogohlantirish sifatida*). Bu albatta qat'iy qonun emas, lekin kelajakda o'zgaruvchilar orasida konstant qiymatlarni ajratish uchun yaxshi usul.

```python
PI = 3.14159
raduis = 21.2
```

## BIR NECHTA O'ZGARUVCHIGA QIYMAT BERISH

Birdaniga bir nechta o'zgaruvchiga qiymat berish uchun o'zgaruvchilar va ularga mos qiymatlar vergul `(,)` bilan ajratiladi:

```python
x, y, z = 10, -7.25, -30
```

Yuqoridagi kod `x` ga `10`, `y` ga `-7.25`, va `z` ga `-30` qiymatini yuklaydi.

## O'ZGARUVCHI TURINI ALMASHTIRISH

Keling quyidagi misolni ko'raylik, maqsadimiz `ism` va `yosh` degan ikki o'zgaruvchini yangi `xabar` degan o'zgaruvchiga yuklab, `"Jobir 16 yoshda"` degan matnni konsolga chiqarish:

```python
ism = 'Jobir'
yosh = 36
xabar = ism + ' ' + yosh + ' yoshda'
print(xabar)
```

Natija: **`TypeError: can only concatenate str (not "int") to str`**

Afsuski, kutilgan natija o'rniga xatolik chiqdi. Agar xatoni ingliz tilidan tarjima qilsak, matn (str) va son (int) ni jamlab bo'lmaydi degan ma'no chiqadi.

Demak Pythonda matn (string) va son (int, float) turidagi o'zgaruvchilarni jamlab bo'lmas ekan. Xo'sh, bunga yechim bormi? **Albatta**.

Pythonda bir turdagi o'zgaruvchini boshqa turga o'tkazish mumkin, bu ingliz tilida ***typecasting*** detiladi. Buning uchun Pythonda mahsus funktsiyalar bor, keling ular bilan tanishamiz:

* `str()`— int yoki float turidagi sonlarni matnga o'zgartiradi.
* `int()`— matn yoki float ko'rinishidagi qiymatlarni butun songa o'zgartiradi. Bunda matn butun son ko'rinishida bo'lishi kerak.
* `float()`— matn yoki int ko'rinishidagi qiymatlarni o'nlik songa o'zgartiradi.

Demak, yuqoridagi kod to'g'ri ishlashi uchun 3-qatorni quyidagicha o'zgartiramiz:

```python
ism = 'Jobir'
yosh = 36
xabar = ism + ' ' + str(yosh) + ' yoshda'
print(xabar)
```

Natija: `Jobir 36 yoshda`

:::danger
`str(yosh)` kodi `yosh` degan o'zgaruvchining qiymatini matn ko'rinishida ko'rsatdi xolos. Asl o'zgaruvchining qiymati sonligicha qoladi. `int()` va `float()`ham huddi shunday ishlaydi.
:::

## O'ZGARUVCHI TURINI TEKSHIRISH

Kodimizda o'zgaruvchilar ko'payib ketdi. Yuqoridagi kabi xatolar qilmaslik uchun ba'zida o'zgaruvchinig turini tekshrish talab qilinadi. Buning uchun `type()` funktsiyasidan foydalanamiz:

```python
ism = 'Jobir'
yosh = 36
print(type(ism))  # ism degan o'zgaruvchining turini konsolga chiqaramiz
print(type(yosh)) # ismyosh degan o'zgaruvchining turini konsolga chiqaramiz
```

Natija:

`<class 'str'>`

`<class 'int'>`

Kurib turganingizdek, `ism` nomli o'zgaruvchi`'str'` ya'ni matn, `yosh` esa `'int'` son turida ekan.

## `INPUT()` VA SONLAR

Avvalgi darsimizda foydalanuvchidan ma'lumot olish uchun input() funktsyasidan foydalanishni o'rgandik. Kelin endi shu funktsiya yordamida foydalanuvchidan son olishni ko'raylik. Quyidagi kod foydalanuvchining tug'ilgan yilini so'raydi va uning yoshini hisoblab beradi:

```python
#1 foydalanuvchining tug'ilgan yilini so'raymiz
t_yil = input("Tug'ilgan yilingizni kiriting: ")
#2 foydalanuvchi yoshini xisoblaymiz
yosh = 2020 - t_yil # 
#3 foydalanuvchi yoshini konsolga chiqaramiz
print("Siz " + yosh + " yoshda ekansiz")
```

![](../cirth-assets/cc1bb3d9-395a-42e6-9d5f-9daaa776fca5.png)

Natija: **`TypeError: unsupported operand type(s) for -: 'int' and 'str'`**

Kutilgan natija o'rniga xatolik. Lekin xato qayerda? Dastur tug'ilgan yilimni so'radi, men `1983` deb kiritdim va shu zaxoti xato ro'y berdi va dastur to'xtadi. Xatoni tarjima qilsak son (int) va matn (str) o'rtasida ayirish (`-`) amalini bajarib bo'maydi deyapti.

Gap shundaki, `input()` funktsiyasi har qanday kiritilgan qiymatni matn (string) ko'rinishida qabul qiladi (garchi biz son kiritgan bo'lsak ham). Keling, konsolda `t_yil` degan o'zgaruvchining turini tekshirib ko'ramiz.

![](../cirth-assets/8f3802c0-349b-4957-ad6a-e451e79bd955.png)

Ko'rib turganingizdek `t_yil` o'zgaruvchisi saqlayotgan qiymat `str` ya'ni matn ekan. Kodimizning 2 va 6-qatorlarini o'zgartiramiz:

```python
#1 foydalanuvchining tug'ilgan yilini so'raymiz va qiymatni int ga aylantiramiz
t_yil = int(input("Tug'ilgan yilingizni kiriting: "))
#2 foydalanuvchi yoshini xisoblaymiz
yosh = 2020 - t_yil # 
#3 foydalanuvchi yoshini konsolga chiqaramiz
print("Siz " + str(yosh) + " yoshda ekansiz")
```

Natija:

`Tug'ilgan yilingizni kiriting: 1983`

`Siz 37 yoshda ekansiz`

Yuqoridagi kodning 2-qatoriga e'tibor bersangiz, biz ikki funktsiyani bir biriga joylab yozdik (`int(input()`). Aslida, ajratib ham yozishimiz mumkin edi:

```python
#1.1 foydalanuvchining tug'ilgan yilini so'raymiz
t_yil = input("Tug'ilgan yilingizni kiriting: ")
#1.2 t_yil o'zgaruvchini int ga aylantiramiz
t_yil = int(t_yil)
#2 foydalanuvchi yoshini xisoblaymiz
yosh = 2020 - t_yil # 
#3 foydalanuvchi yoshini konsolga chiqaramiz
print("Siz " + str(yosh) + " yoshda ekansiz")
```

## AMALIYOT

Quyidagi dasturlarning har birini alohida fayl ko'rinishida yozing va bajaring:

* Foydalanuvchi kiritgan sonning kvadrati va kubini konsolga chiqaruvchi dastur

![](../cirth-assets/23e3f88d-8e51-4471-a691-7b79cadc8450.png)

* Foydalanuvchining yoshini so'rab, uning tug'ilgan yilini hisoblab, konsolga chiqaruvchi dastur

![](../cirth-assets/717634cf-2a1e-4a0e-b174-adc06fdbc21f.png)

* Foydalanuvchidan ikki son kiritshni so'rab, kiritilgan sonlarning yig'indisi, ayirmasi, ko'paytmasi va bo'linmasini chiqaruvchi dastur

![](../cirth-assets/835f88f6-ace7-4207-93d7-30fe704ac740.png)

## JAVOBLAR

<Embed url="https://repl.it/@anvarbek/javoblar-06-dars#main.py" />

<FileBlock src="https://1283015017-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-MGbkqs1tROquIT6oqUs%2F-MLounVATri6iU10sCuw%2F-MLqbwIKkxmaWCjSoGkS%2F06-dars-javoblar.zip?alt=media&token=530d01ec-034e-486c-a16d-a92fb5e81b55" size="1.2 KB" />