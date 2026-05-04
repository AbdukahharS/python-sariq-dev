# #31 INKAPSULYATSIA, KLASSNING XUSUSIYAT VA METODLARI

<Embed url="https://youtu.be/B7kS9lC1fWg" />

## INKAPSULYATSIYA

Obyektga Yo'naltirilgan Dasturlashning tamoyillaridan biri bu inkapsulyatsiya, ya'ni obyektning xususiyatlarga to'g'ridan-to'g'ri (nuqta orqali) murojat qilishni va ularning qiymatini o'zgartirishni taqiqlab qo'yish. Pythonda bunday yopiq xususiyatlarning nomi ikki pastki chiziq bilan boshlanadi:

```python
from uuid import uuid4
class Avto:
    """Avtomobil klassi"""
    def __init__(self,make,model,rang,yil,narh,km=0):
        """Avtomobilning xususiyatlari"""
        self.make = make
        self.model = model
        self.rang = rang
        self.yil = yil
        self.narh = narh
        self.__km = km
        self.__id = uuid4()
    
    def get_km(self):
        return self.__km
    
    def get_id(self):
        return self.__id
```

Yuqoridagi kodimizning 11-qatorida `__km` xususiyati avtomobilning necha km yurgani haqida ma'lumot saqlaydi va bu ma'lumotni tashqaridan o'zgartirib bo'lmaydi. Kodimizning 12-qatorida esa har bir yangi yaratilgan avtomobilga yangi, noyob va takrorlanmas ID generasiya qilish uchun uuid4() funksiyasidan foydalanayapmiz. Deylik biz mashinalar sotish uchun onlayn bozor yaratsak, bozorimizga qo'shilgan har bir moshina endi o'zining ID raqamiga ega bo'ladi va bu ID raqamni to'g'ridan-to'g'ri (nuqta orqali) ko'rib bo'lmaydi.

```python
avto1 = Avto("GM","Malibu","Qora",2020,40000,100000)
avto1.__km
```

Natija: `AttributeError: 'Avto' object has no attribute '__km'`

Yopiq xususiyatlarni ko'rish uchun esa alohida metodlar yozish maqsadga muvofiq bo'ladi (`get_km()` va `get_id()`):

```python
print(f"ID: {avto1.get_id()}")
```

Natija: ID: `1d4f39a4-3222-4682-9231-6275ca5e1bff`

Bunday yopiq xususiyatlarni o'zgartirish ham metodlar orqali amalga oshirilishi kerak. Misol uchun mashinaning necha km yurganini o'zgartirish uchun klassimizga quyidagi metodni qo'shamiz:

```python
    def add_km(self,km):
        """Mashinaning km ga yana km qo'shish"""
        if km>=0:
            self.__km += km
        else:
            print("Mashina km kamaytirib bo'lmaydi")
```

```python
avto1.add_km(1500)
print(avto1.get_km())
```

Natija: `101500`

Inkapsulyatsiyaning maqsadi obyektning ma'lum xususiyatlarini tashqi ta'sirdan himoya qilish. Misol uchun yuqoridagi misolimizda mashinaning qancha yurganini faqat musbat tarafga o'zgartirish mumkin, noyob ID raqamini esa umuman o'zgartirib bo'lmaydi.

## KLASSNING XUSUSIYATLARI VA METODLARI

Avvalgi darslarimizda biror klassdan yaratilgan har bir obyektning xususiyatlarini klass ichidagi`def __init__()` medoti yordamida berayotgan edik. Bu metod qanday ishlaydi? Biz har gal klassga murojat qilganimizda klass aynan shu `__init__`metodini ishga tushiradi va biz bergan xususiyatlar bilan yangi obyekt yaratadi.

Pythonda xususiyatlarni nafaqat obyektga balki to'g'ridan-to'g'ri klassga ham yuklash imkoniyati mavjud. Bunda klassning xususiyatiga berilgan qiymat barcha obyektlar uchun umumiy bo'ladi. Bu xususiyatni bir obyekt orqali o'zgartirilganda shu klassga oid barcha obyektlarda ham uning qiymati o'zgaradi.

Klassga oid xususiyatlar `def __init__()` metodidan avval e'lon qilinadi.

Keling tushunarli bo'lishi uchun quyidagi misolni ko'ramiz:

```python
class Avto:
    """Avtomobil klassi"""
    num_avto = 0
    def __init__(self,make,model,rang,yil,narh,km=0):
        """Avtomobilning xususiyatlari"""
        self.make = make
        self.model = model
        self.rang = rang
        self.yil = yil
        self.narh = narh
        self.__km = km
        self.__id = uuid4()
        Avto.num_avto += 1
```

Kodni tahlil qilamiz:

- 1-qatroda Avto klassini e'lo qildik
- 3-qatorda Avto klassiga oid bo'lgan xususiyat `num_avto` yaratdik va unga 0 qiymatini berdik
- Keyingi qatorlarda `__init__` metodi yordamida klassdan yaratiladigan obyektlarning xususiyatlarini e'lon qildik va har gal bu metdoga murojat qilingandan `num_avto` ning qiymatini `1` ga oshradigan qilib qo'ydik (13-qator).

Yuqoridagi usul bilan endi biz dastur davomida Avto klassidan jami nechta obyektlar yaratilganini kuzatib borishimiz mumkin bo'ladi. Bunda num\_avto o'zgaruvchisiga istalgan obyekt orqali yoki klass nomi orqali murojat qilish mumkin:

```python
avto1 = Avto("GM","Malibu","Qora",2020,40000)
avto2 = Avto("GM","Lacetti","Oq",2020,20000)
print(avto1.num_avto)
```

Natija: `2`

```python
avto3 = Avto("Toyota",'Carolla',"Silver",2018, 45000)
print(Avto.num_avto)
```

Natija: `3`

### KLASSNING XUSUSIYATLARINI INKAPSULYATSIYA QILISH

Klassga oid xususiyatlar ham huddi yuoqridagi kabi nomidan avval ikki pastki chiziq qo'shish bilan inkapsulyatsiya qilinadi:

```python
class Avto:
    """Avtomobil klassi"""
    __num_avto = 0 # klassga oid xususiyat
    def __init__(self,make,model,rang,yil,narh):
        """Avtomobilning xususiyatlari"""
        self.make = make
        self.model = model
        self.rang = rang
        self.yil = yil
        self.narh = narh
        Avto.__num_avto += 1
```

### KLASSGA OID METODLAR

Klasslarning o'ziga xos metodlari ham bo'lishi mumkin. Misol uchun yuqoridagi num\_avto xususiyatini ko'rish uchun alohida metod yozishimiz mumkin. Klassga oid metodlar @classmethod dekoratori bilan boshlanadi va obyektga oid metodlardan farqli ravishda _`self`_ emas _`cls`_ (class) argumentini qabul qiladi.

```python
class Avto:
    """Avtomobil klassi"""
    __num_avto = 0
    def __init__(self,make,model,rang,yil,narh,km=0):
        """Avtomobilning xususiyatlari"""
        self.make = make
        self.model = model
        self.rang = rang
        self.yil = yil
        self.narh = narh
        self.__km = km
        self.__id = uuid4()
        Avto.__num_avto += 1
    
    @classmethod
    def get_num_avto(cls):
        return cls.__num_avto
```

Klass metodlarga klassning nomi orqali murojat qilinadi:

```python
avto1 = Avto("GM","Malibu","Qora",2020,40000)
avto2 = Avto("GM","Lacetti","Oq",2020,20000)
avto3 = Avto("Toyota",'Carolla',"Silver",2018, 45000)
print(Avto.get_num_avto())
```

Natija: `3`

:::info
`@classmethod` bu maxsus dekorator. Dekoratorlar bu o'z ichiga funksiya oluvchi funksiyalar. Dekoratorlar haqida keyingi darslarimizning birida batafsil to'xtalamiz.
:::

## KLASSLARNI MODULGA AJRATISH

Vaqt o'tishi bilan dasturimizda klasslar ko'payib borishi tabiiy. Bizning asosiy dasturimiz uzun va chigal bo'lmasligi uchun klasslarni ham huddi funksiyalar kabi alohida modullarga ajratish maqsadga muvofiq bo'ladi. Dastur davomida kerak bo'ladigan klasslarga esa modulni chaqirish (import) orqali murojat qilishimiz mumkin. Bunda, bir-biriga bog'liq klasslarni bitta faylga joylashimiz mumkin.

Misol uchun, biz `Talaba`, `Professor`, `Foydalanuvchi` va `Shaxs` degan klasslarni bitta `odamlar.py` moduliga, `Avto`, `Bus`, `Train` degan klasslarni esa boshqa `transport.py` moduliga joyladik. Kelajakda biz bu klasslarga import orqali murjat qilishimiz mumkin.

### BITTA KLASSNI IMPORT QILISH

Moduldan bitta klass import qilish uchun `from`` `**`modul`**` ``import`` `**`klass`** ifodasidan foydalanamiz:

```python
from odamlar import Talaba
from transport import Avto

talaba = Talaba("Alijon","Valiyev","FA010101","N00022")
avto = Avto("GM","Malibu","Qora",2020,40000)
```

### BIR NECHTA KLASSLARNI IMPORT QILISH

Moduldan bir nechta klass chaqirish talab qilinsa, `import` so'zidan so'ng klasslar ketma-ket vergul bilan ajratib yoziladi:

```python
from odamlar import Talab, Shaxs

talaba = Talaba("Alijon","Valiyev","FA010101","N00022")
shaxs = Shaxs("Hasan","Husanov","FB0011223")
```

### MODULNI O'ZINI CHAQIRISH

Modulni to'liq import qilish uchun `import modul` ifodasidan foydalanamiz. Bunda modul ichidagi klasslarga modul nomi va nuqta orqali murojat qilinadi:

```python
import odamlar
talaba = odamlar.Talaba("Alijon","Valiyev","FA010101","N00022")
shaxs = odamlar.Shaxs("Hasan","Husanov","FB0011223")
```

### MODULDAGI BARCHA KLASSLARNI IMPORT QILISH

Moduldagi barcha klasslar quyidagicha import qilinadi: `from modul import *`. Bunda modul ichidagi istalgan klassga to'g'ridan-to'g'ri uning nomi bilan murojat qilinadi.

```python
from odamlar import *
talaba = Talaba("Alijon","Valiyev","FA010101","N00022")
shaxs = Shaxs("Hasan","Husanov","FB0011223")
```

Bu usul 2 sababga ko'ra tavsiya qilinmaydi:

1. Dasturni kelajakda qayta ochganimizda, dastur davomida moduldagi aynan qaysi klasslardan foydalanganimizni bir qarashda bilib bo'lmaydi
1. Agar modul juda katta bo'lsa, uning ichidagi ba'zi klasslar biz o'zimiz yaratgan klasslar bilan nomi bir hil bo'lib qolish ehtimoli bor. Bu esa o'z navbatida dastrumiz xato ishlashiga olib keladi.

:::info
Modul ichiga boshqa modulni ham import qilish mumkin. Masalan modul ichidagi ba'zi klasslar to'g'ri ishlashi uchun boshqa modul talab qilingan vaqtlarda.
:::

## AMALIYOT

- Avvalgi darslarimizda yaratgan `Shaxs` va `Talaba` klasslariga yopiq xususiyatlar qo'shing va ularning qiymatini ko'rsatuvchi va o'zgartiruvchi metodlar yozing.
- Yuqoridagi klasslarga `talabalar_soni` va `odamlar_soni` degan klassga oid xususiyatlar qo'shing.
- Klassga oid xususiyatlar bilan ishlash uchun maxsus `@classmethod` lar yozing
