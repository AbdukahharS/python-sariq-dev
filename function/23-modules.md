# #23 MODULLAR

<Embed url="https://www.youtube.com/watch?v=SEQzCcXY4Pc&feature=youtu.be" />

## MODUL NIMA?

Funksiyaning qulayliklaridan biri, ko'p takrorlanadigan kodlarni funksiya ichida yashirishimiz va kerak bo'lgan murojat qilishimiz mumkinligida. Maqsadimiz dasturimizni ixcham va tushunarli qilib, kelajakda o'zimiz yoki boshqalar uchun ham "toza" kod qoldrisih. Bu yo'nalishda yana bir qadam qo'yib, dasturimizni modullarga ajratimshimiz mumkin.

Modul bu loyihamiz ichidagi alohida fayl bo'lib, dasturimiz davomida ishlatiladigan funskyalarni (va o'zgaruvchilarni) mana shu faylga joylab, ko'zdan yashirib qo'yishimiz mumkin. Bu bizga asosiy dasturimizdan chalg'imasdan kod yozish imkoniyatini beradi.

Modul va uning ichidagi funksiyalarni istalgan payt asosiy dasturimizga yuklab olishimiz, modullarni boshqa dasturchilar bilan ulashishimiz yoki kelajakda o'zimizning boshqa loyihalarimizda foydalanishimiz mumkin.

Umuman olganda katta dasturlar bir nech o'nlab modullardan iborat bo'lishi tabiiy hol.

## MODUL YARATAMIZ

Modul yaratish uchun asosiy dasturimizdagi funksiyalarni yangi faylga ko'chiramiz xolos. Modulga oson murojat qilishimiz uchun, faylimiz asosiy dasturimiz bilan bitta papkada bo'lgani afzal. Bunda adashib ketmaslik uchun, loyihangizning (dasturning) asosiy faylini `main.py` deb nomlash o'rinli.

Keling, biz ham `avto_info_mod.py` degan fayl yaratamiz va ichiga quyidagi 3 ta funksiyalarni joylaymiz:

```python
def avto_info(kompaniya, model, rangi, korobka, yili, narhi=None):
    """Avtomobil haqidagi ma'lumotlarni lug'at ko'rinishida qaytaruvchi funksiya"""
    avto = {'kompaniya':kompaniya,
            'model':model,
            'rang':rangi,
            'korobka':korobka,
            'yil':yili,
            'narh':narhi}
    return avto

def avto_kirit():
    """Foydalanuvchiga avto_info funksiyasi yordamida bir nechta avtolar haqida ma'lumotlarni bitta ro'yxatga joylash imkonini beruvchi funksiya"""
    avtolar=[] # salondagi avtolar uchun bo'sh ro'yxat
    while True:
        print("\nQuyidagi ma'lumotlarni kiriting",end='')
        kompaniya=input("Ishlab chiqaruvchi: ")
        model=input("Modeli: ")
        rangi=input("Rangi: ")
        korobka=input("Korobka: ")
        yili=input("Ishlab chiqarilgan yili: ")
        narhi=input("Narhi: ")    
        #Foydalanuvchi kiritdan ma'lumotlardan avto_info yordamida 
        #lug'at shakllantirib, har bir lug'atni ro'yxatga qo'shamiz:
        avtolar.append(avto_info(kompaniya, model, rangi, korobka, yili, narhi))    
        # Yana avto qo'shish-qo'shmaslikni so'raymiz
        javob = input("Yana avto qo'shasizmi? (yes/no): ")
        if javob=='no':
            break
    return avtolar

def info_print(avto_info):
    """Avtomobillar haqida ma'lumotlar saqlangan lug'atni konsolga chiqaruvchi funksiya"""
    print(f"{avto_info['rang'].title()} {avto_info['kompaniya'].upper()} "
          f"{avto_info['model'].upper()}, {avto_info['korobka']} korobka, "
          f"{avto_info['yil']}-yil, {avto_info['narh']}$")
```

Yuqoridagi funksiyalarga asosiy dasturdan murojat qlishning bir necha usuli bor.

## MODULNI CHAQIRIB OLISH

Modul ichidagi istalgan funksiyaga murojat qilish uchun `import modul_nomi` komandasidan foydalanamiz. Bunda modul ichidagi istalgan funksiyaga `modul_nomi.funksiya_nomi()` ko'rinishida murojat qilishimiz mumkin. Ya'ni avval modul nomi undan keyin esa nuqta qo'yilib, modul ichidagi funksiya nomi yoziladi.

Keling, yuqoridagi modulimizdagi `avto_info()` va `info_print()` funksiyalariga murojat qilamiz:

```python
import avto_info_mod # avto_info_mod faylini (modulini) chaqiramiz

avto1 = avto_info_mod.avto_info("GM", "Malibu", "Qora", "avtomat", 2020,40000)
avto_info_mod.info_print(avto1)
```

Natija: `Qora GM MALIBU, avtomat korobka, 2020-yil, 40000$`

Ko'rib turganingizdek, dasturimiz qisqa, tushunarli va muhimi toza bo'ldi. 3 qator kod ortida 20 qatordan ortiq kodni yashirdik.

:::info
**`import`**` ``modul_nomi` komandasi bir martta, dastur boshida yoziladi.
:::

### MODULGA QISQA NOM BERISH

Yuqoridagi usul bilan modulni chaqirib olishda fayl nomi uzun bo'lsa bu o'ziga yarasha noqulayliklar tug'dirishi mumkin. Buning oldini olish uchun esa, modulni chaqirganda unga `as` operatori yordamida qisqa nom berishimiz, va modulga qisqa nom orqali murojat qilish mumkin. Quyidagi misolda `avto_info_mod` ni qisqa qilib `aim` deb nomlab oldik, va 3-4-qatorlarda modulga murojat qilishda qisqa nomidan foydalandik.

```python
import avto_info_mod as aim # avto_info_mod ni qisqa nom aim bilan chaqiramiz

avto1 = aim.avto_info("GM", "Malibu", "Qora", "avtomat", 2020,40000)
aim.info_print(avto1)
```

:::danger
Modulga qisqa nom berganingizda bunday nomli boshqa o'zgaruvchi yoki funksiya yo'qligiga amin boling. Shunigdek, dastur davomida bu nomni boshqa o'zgaruvchilarga yoki funksiylarga berib yubormang.
:::

## MODUL ICIHDAN MA'LUM FUNKSIYALARNI KO'CHIRIB OLISH

Agar katta modullardan faqatgina ba'zi funksiyalarga murojat qilish talab qilinisa, kerakli funksiyalarni **`from`**` ``modul_nomi`` `**`import`**` ``funksiya1, funksiya2` komandasi yordamida o'zimizning dasturimizga ko'chirib olishimiz mumkin. Bu usulning qulayligi, endi funksiyalarga to'g'ridan-to'g'ri murojat qilish mumkin (modul ismini yozmagan holda).

Misol uchun avvalgi kodimizda biz faqatgina `avto_info` va `info_print` funksiyalaridan foydalandik. Shu funksiyalarni asosiy kodimizga ko'chirib olaylik:

```python
from avto_info_mod import avto_info, info_print

avto1 = avto_info("GM", "Malibu", "Qora", "avtomat", 2020,40000)
info_print(avto1)
```

### FUNKSIYALARGA QISQA NOM BERISH

Huddi avvalgidek, ko'chrib olgan funksiyamizga ham qisqa nom berishimiz mumkin.

```python
from avto_info_mod import avto_info as ainfo, info_print as iprint

avto1 = ainfo("GM", "Malibu", "Qora", "avtomat", 2020,40000)
iprint(avto1)
```

## MODUL ICHIDAGI BARCHA FUNKSIYALARNI KO'CHIRIB OLISH

Modul ichidagi barcha funksiyalarni asosiy dasturga ko'chirib olish uchun `from modul_nomi import *` komandasidan foydalanamiz.

```python
from avto_info_mod import *

avto1 = avto_info("GM", "Malibu", "Qora", "avtomat", 2020,40000)
info_print(avto1)
```

:::danger
Diqqat! Bir necha sabablarga ko'ra bu usuldan foydalanish tavsiya qilinmaydi. Katta modullarda yuzlab funksiyalar bo'lishi mumkin, va funksiya nomi sizning dasturingizdagi boshqa funksiya yoki o'zgaruvchi bilan bir hil nomga ega bo'lsa, dastur xato ishlashiga olib keladi.
:::

## MODULDA O'ZGARUVCHI SAQLASH

Modullarning ichida nafaqat funksiyalar, balki turli o'zgaruvchilarni ham saqlash mumkin. Modul ichidagi o'zgaruvchilarga ham huddi yuqoridagi usullar bilan murojat qilish mumkin.

## PYTHON MODULLARI

Python dasturlash tili tayyor modullar bilan keladi, modullarning to'liq ro'yxatini quyidagi bo'glama orqali kirib ko'rishingiz mumkin:

<Embed url="https://docs.python.org/3/py-modindex.html" />

Keling ulardan ba'zilari bilan tanishamiz.

### `math` MODULI

Bu modulda matematik hisob kitoblarni bajaruvchi funksiyalar va o'zgaruvchilar joylashgan. Keling ularga ba'zi misollarni ko'ramiz.

#### `sqrt()` - qavs ichida berilgan qiymatning kvadrat ildizini qaytaradi

```python
import math

x=400
print(math.sqrt(x))
```

Natija: `20.0`

#### `pow(x,y)` - x ning y-darajasini qaytaradi

```python
print(pow(5,5))
```

Natija: `3125`

#### pi - $$\pi$$ ning qiymatini saqlovchi o'zgaruvchi

```python
from math import pi
print(pi)
```

Natija: `3.141592653589793`

#### `log2(x)` va `log10(x)` - `x` ning 2 va 10-lik logorifmini qaytaruvchi funksiyalar

```python
print(math.log2(8))
print(math.log10(100))
```

#### `math` ichidagi ayrim funksiyalar

| Funksiya     | Funksiya ta'rifi                                               |
| ------------ | -------------------------------------------------------------- |
| `ceil(x)`    | x dan katta yoki teng bo'lgan eng kichik butun sonni qaytaradi |
| `fabs(x)`    | x ning absolyut qiymatini qaytaradi                            |
| `floor(x)`   | x dan kichik yoki teng bo'lgan eng yaqin butun sonni qaytaradi |
| `exp(x)`     | $$x^e$$ ni qaytaruvchi funksiya                                |
| `cos(x)`     | $$\cos(x)$$ ni qaytaruvchi funksiya                            |
| `sin(x)`     | $$\sin(x)$$ ni qaytaruvchi funksiya                            |
| `tan(x)`     | $$\tan(x)$$ ni qaytaruvchi funksiya                            |
| `degrees(x)` | x burchakning radian qiymatini darajaga konvertasiya qilish    |
| `radians(x)` | x burchakning daraja qiymatini radianga konvertasiya qilish    |
| `e`          | Matematik konstanta $$e$$ (2.71828...)                         |

[`math` moduli](https://docs.python.org/3/library/math.html#module-math) ichidagi barcha funksiyalar bilan [Pythonning rasmiy sahifasida ](https://docs.python.org/3/library/math.html#module-math)tanishishingiz mumkin.

### `random` MODULI

Random moduli tasodifiy sonlar bilan ishlash uchun qulay funksiyalarga boy. Keing ulardan ayrimlari bilan tanishamiz.

#### `randint(a,b)`

Bu funksiya a va b oraligi'da tasodifiy butun son qaytaradi.

```python
import random as r # random modulini r deb chaqirayapmiz

son = r.randint(0,100) # 0 va 100 oralig'ida tasodifiy son
print(son)
```

#### `choice(x)`

`x` ning ichidan tasodifiy qiymatni qaytaruvchi funksiya. Bunda `x` bir necha elementdan iborat o'zgaruvchi (matn, ro'yxat) bo'lishi kerak.

```python
ismlar = ['olim','anvar','hasan','husan']
ism = r.choice(ismlar) # ismlar dan tasodifiy ism tanlaymiz
print(ism)
print(r.choice(ism)) # ismdan tasodifiy harf tanlaymiz
```

![Natija](../cirth-assets/81034190-0278-4db9-b28c-353ff5f32748.png)

```python
x = list(range(0,51,5))
print(x)
print(r.choice(x))
```

![Natija](../cirth-assets/fead1563-2686-4c15-a7f3-4f35073b88f9.png)

**shuffle(x)**

`x` ichidagi elementlarni tasodifiy tartibda qaytaruvchi funksiya. Bunda `x` bir necha elementdan iborat o'zgaruvchi (matn, ro'yxat) bo'lishi kerak.

```python
x = list(range(11))
print(x)
r.shuffle(x)
print(x)
```

![Natija](../cirth-assets/8d936ee3-0834-4738-a027-3dafd4f5279b.png)

`random` moduli ichidagi boshqa funksiyalar haqida [Python rasmiy sahifasidan](https://docs.python.org/3/library/random.html#module-random) ma'lumot olishingiz mumkin.