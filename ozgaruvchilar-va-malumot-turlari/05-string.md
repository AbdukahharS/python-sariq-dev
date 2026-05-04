# #05 STRING (MATN)

<Embed url="https://www.youtube.com/watch?v=ne2ZoZ7q3UY" />

## **STRING VA UNICODE**

**STRING** (matn) —Pythondagi eng mashxur ma'lumot turlaridan biri. Avvalgi darsda ko'rganimizdek, o'zgaruvchiga matn yuklash uchun matn qo'shtirnoq (`" "`) yoki birtirnoq (`' '`) ichida yozilishi kerak.

```python
shahar = "Қўқон"
viloyat = 'Фарғона'
```

Pythonda matnlar [Unicode ](https://unicode-table.com/en/)jadvalidagi istalgan belgilaridan iborat bo'lishi mumkin (jumladan o'zbek, arab, hind, xitoy alifbosidagi harflar yoki turli emoji-smayliklar).

```python
matn = "Men yangi 📱 oldim"
print(matn)
```

Natija: `Men yangi 📱 oldim`

![UNICODE jadvalidagi harf va belgilarga misol](../cirth-assets/d8d67da9-56aa-42f5-999c-001883a90cdd.png)

## STRING USTIDA AMALLAR

### Matnlarni qo'shish operatori (`+`)

Matnlarni qo'shish uchun `+` operatoridan foydalanmiz:

```python
ism = 'Ahmad'
print("Mening ismim " + ism)
```

Natija: `Mening ismim Ahmad`

```python
ism = 'Ahad'
familiya = 'Qayum'
print(ism + familiya)
```

Natija: `AhadQayum`

Yuqoridagi kodda ism va familiya orasiga bo'shliq belgisini qo'shmaganimiz uchun ikki matn qo'shilib yozildi. Buni to'g'rilash uchun, 3-qatorni quyidagicha yozamiz:

```python
ism = 'Ahad'
familiya = 'Qayum'
print(ism + ' ' + familiya) # ikki o'zgaruvchi orasiga bo'sh joy qo'shamiz
```

Natija: `Ahad Qayum`

### f-string

Ikki (va undan ko'p) matn ko'rinishidagi o'zgaruvchilarni birlashtirish uchun f-string usulidan  `f"{matn1} {matn2}"` ham foydalansak bo'ladi:

```python
ism = "Ahad"
familiya = 'Qayum'
ism_sharif = f"{ism} {familiya}"
print(ism_sharif)
```

Bu usul yordamida uzun matnlarni ham yasash mumkin:

```python
ism = "James"
familiya = 'Bond'
print(f"Salom, mening ismim {familiya}. {ism} {familiya}!")
```

Natija: `Salom, mening ismim Bond. James Bond!`

### Mahsus belgilar

Matnga bo'shliq qo'shish uchun `\t` belgisidan, yangi qatordan boshlash uchun `\n` belgisidan foydalanamiz:

```python
print('Hello World!')
print('Hello \tWorld!')
print('Hello \nWorld!')
```

Natija:

`Hello World!`

`Hello    World!`

`Hello`

`World!`

## STRING METODLARI

Pythonda string ustida amalga oshirish mumkin bo'lgan tayyor amallar to'plami mavjud. Bunday amallar to'plami **metodlar** deb ataladi.

Metodlarni qo'llash uchun metod nomi matndan so'ng `.metod_nomi()` ko'rinishida yoziladi. Keling shunday metodlarning ba'zilari bilan tanishaylik.

### `upper()` va `lower()` metodlari

`upper()` metodi matndagi har bir harfni katta harfga o'zgartiradi.

```python
ism = 'Ahad'
familiya = 'Qayum'
ism_sharif = f"{ism} {familiya}"
print(ism_sharif.upper())
```

Natija: `AHAD QAYUM`

`lower()` metodi esa aksincha, har bir harfni kichik harfga o'zgartiradi.

```python
ism = 'Ahad'
familiya = 'Qayum'
ism_sharif = f"{ism} {familiya}"
print(ism_sharif.lower())
```

Natija: `ahad qayum`

### `title()` va `capitalize()` metodlari

`title()` metodi matndagi har bir so'zning birinchi harfini katta harf bilan yozadi.

```python
ism_sharif = 'james bond'
print(ism_sharif.title())
```

Natija: `James Bond`

`capitalize()` esa faqatgina eng birinchi so'zning birinchi harfini katta bilan yozadi.

```python
ism_sharif = 'james bond'
print(ism_sharif.capitalize())
```

Natija: `James bond`

Metodlarni faqat o'zgaruvchilarga emas, balki to'g'ridan-to'g'ri matnga ham qo'llash mumkin (aslida o'zgaruvchi ham matnning (yoki boshqa ma'lumotning) manzili xolos)

```python
print('james bond'.upper())
```

Natija: `JAMES BOND`

### `strip()`, `rstrip()` va `lstrip()` metodlari

Bu metodlar matnning boshi va oxiridagi bo'sh joylarni olib tashlaydi.

* `lstrip()` — matn boshidagi bo'shliqni,
* `rstrip()` – matn oxiridagi bo'shliqni,
* `strip()` — matn boshi va oxiridagi bo'shliqlarni olib tashlaydi

```python
meva = "     olma     "
print("Men " + meva.lstrip() + " yaxshi ko'raman")
print("Men " + meva.rstrip() + " yaxshi ko'raman")
print("Men " + meva.strip() + " yaxshi ko'raman")
print("Men " + meva + " yaxshi ko'raman")
```

> Men olma      yaxshi ko'raman
>
> Men       olma yaxshi ko'raman
>
> Men olma yaxshi ko'raman
>
> Men       olma      yaxshi ko'raman

Matnlar bilan ishlaydigan metodlar ko'p. Ularning ba'zilari bilan kelajakda yana tanishamiz, to'liq ro'yhatni esa quyidagi [sahifada ](https://www.w3schools.com/python/python_ref_string.asp)ko'rishingiz mumkin.

:::danger
**Metodlar o'zgaruvchi ichidagi asl matnni o'zgartirmaydi!**
:::

## INPUT —FOYDALANUVCHI BILAN MULOQOT

Shu paytgacha biz o'zgaruvchilarning qiymatini dasturning ichida berayotgan edik. Keling endi qiymatni o'zimiz emas, balki dastur foydalanuvchilariga kiritish imkonini beramiz.

Buning uchun `input()` funktsyasidan foydalanamiz.

```python
ism = input("Ismingiz nima?")
print("Assalom alaykum, " + ism)
```

Yuqoridagi dastur, avval 1-qatorda foydalanuvchining ismini so'raydi. Foydalanuvchi ismini kiritib, **Enter** tugmasini bosgach, foydalanuvchi kiritgan matn`ism` degan o'zgaruvchiga yuklanadi va dasturining 2-qatori bajaradi:

Natija:

`Ismingiz nima?anvar`

`Assalom alaykum, anvar`

Keling yuqoridagi kod va uning natijasini chiroyliroq ko'rinishga keltiramiz.

```python
ism = input("Ismingiz nima?\n>>>") # Foydalanuvchi ismini yangi qatordan kiritadi
print("Assalom alaykum, " + ism.title())
```

![Foydalanuvchidan qiymat olish](../cirth-assets/54adc7c5-d8d8-4ff0-8006-0e1caf521d8b.gif)

## AMALIYOT

Quyidagi mashqlarni bajaring:

* Quyidagi o'zgaruvchilarni yarating:
  * `kocha="Bog'bon"`
  * `mahalla="Sog'bon"`
  * `tuman="Bodomzor"`
  * `viloyat="Samarqand"`
* Yuqoridagi o'zgaruvchilarni jamlab, quyidagi ko'rinishda konsolga chiqaring:
  * `Bog'bon ko'chasi, Sog'bon mahallasi, Bodomzor tumani, Samarqand viloyati`
* Yuqoridagi o'zgaruvchilarning (`kocha`, `mahalla`, `tuman`, `viloyat`) qiymatini foydalanuvchidan so'rang. Va avvalgi mashqni takrorlang.
* Yuqoridagi matnni konsolga chiqarishda har bir verguldan keyin yangi qatordan yozing
* Yuqoridagi matnni **f-string** yordamida, yangi, `manzil` deb nomlangan o'zgaruvchiga yuklang
* `manzil`ga biz yuqorida o'rgangan `title()`, `upper()`, `lower()` , `capitalize()` metodlarini qo'llab ko'ring.
* Quyidagi o'zgaruvchilarni yarating:
  * `kocha="Bog'bon"`
  * `mahalla="Sog'bon"`
  * `tuman="Bodomzor"`
  * `viloyat="Samarqand"`
* Yuqoridagi o'zgaruvchilarni jamlab, quyidagi ko'rinishda konsolga chiqaring:
  * `Bog'bon ko'chasi, Sog'bon mahallasi, Bodomzor tumani, Samarqand viloyati`
* Yuqoridagi o'zgaruvchilarning (`kocha`, `mahalla`, `tuman`, `viloyat`) qiymatini foydalanuvchidan so'rang. Va avvalgi mashqni takrorlang.
* Yuqoridagi matnni konsolga chiqarishda har bir verguldan keyin yangi qatordan yozing
* Yuqoridagi o'zgaruvchilarni **f-string** yordamida, yangi, `manzil` deb nomlangan o'zgaruvchiga yuklang
* `manzil`ga biz yuqorida o'rgangan `title()`, `upper()`, `lower()` , `capitalize()` metodlarini qo'llab ko'ring.

## JAVOBLAR

<Embed url="https://repl.it/@anvarbek/javoblar-05-dars#main.py" />

<FileBlock src="https://1283015017-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-MGbkqs1tROquIT6oqUs%2F-ML_ohun0-bilUcvvdGp%2F-ML_peXOkZaFAlnuHrpL%2Fjavoblar-05-dars.zip?alt=media&token=219c4363-7b1c-4d2b-877e-88930a206855" size="776 B" />