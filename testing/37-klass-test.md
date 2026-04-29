# #37 KLASSNI TEKSHIRISH

{% embed url="<https://www.youtube.com/watch?v=vsxJPRLXpgI>" %}

## KIRISH

Avvalgi darsimizda funksiyalarni tekshiruvchi testlar yozishni o'rgandik. Ushbu mavzuda esa klasslarni test qilishni o'rganamiz. Klass to'g'ri bo'lsa, undan yaratilgan obyektlar ham to'g'ri ishlaydi.&#x20;

Keling boshlanishiga biror klass yaratamiz:

```python
class Car:
    """(self,make,model,year,km=0,price=None)"""
    def __init__(self,make,model,year,km=0,price=None):
        self.make = make
        self.model = model
        self.year = year
        self.price = price
        self.__km = km
    
    def set_price(self,price):
        self.price = price
        
    def add_km(self,km):
        """Mashinaning km ga yana km qo'shish"""
        if km>=0:
            self.__km += km
        else:
            raise ValueError("km manfiy bo'lishi mumkin emas")
    
    def get_info(self):
        info = f"{self.make.upper()} {self.model.title()}, " 
        info += f"{self.year}-yil, {self.__km}km yurgan."
        if self.price:
            info += f" Narhi: {self.price}"
        return info
       
    def get_km(self):
        return self.__km
```

Yuqoridagi klassimiz avtomobil haqida ma'lumotlarni saqlaydi. Klassimizning e'tibor qaratishimiz kerak bo'lgan jihatlari:

* `km` va `price` (narh) argumentlariga standart qiymat berilgan
* km parametri inkapsulasiyalangan (`self.__km`)
* Avtomobil narhini `set_price()` metodi yordamida yangilash mumkin
* `add_km()` metodi faqat musbat qiymat qabul qiladi. Agar manfiy qiymat uzatilsa `raise` operatori yordamida `ValueError` xatosini qaytaradi
* `get_info()` metodidan qaytadigan qiymat avtomobil narhi bor yoki yo'qligiga qarab turli ko'rinishda bo'lishi mumkin
* Avtomobil kilometrajini ko'rish uchun `get_km()` metodiga murojat qilamiz.

## XUSUSIYATLARNI TEKSHIRISH

Klassdan obyekt yaratish jarayonida biz obyektning xususiyatlarini parametr ko'rinishida beramiz. Quyidagi testda aynan shu jarayon to'g'ri kechganini tekshiramiz:

```python
import unittest
from cars import Car

class CarTest(unittest.TestCase):
    """Car klassini tekshirish uchun test"""
    
    def test_create(self):        
        # avto1 obyektini km va narhini bermasdan yaratamiz
        avto1 = Car("toyota","camry",2020)
        # Qiymatlar mavjudligini assertIsNotNone metodi bilan tekshiramiz
        self.assertIsNotNone(avto1.make)
        self.assertIsNotNone(avto1.model)
        self.assertIsNotNone(avto1.year)
        # Qiymat mavjud emasligini assertIsNone metodi bilan tekshiramiz
        self.assertIsNone(avto1.price)
        # Qiymat tengligini assertEquals metodi bilan tekshiramiz
        self.assertEqual(0,avto1.get_km())
        # Yangi obyekt yaratamiz va narhini ham ko'rsatamiz
        avto2 = Car("toyota","camry",2020,price=75000)
        self.assertEqual(75000,avto2.price)
        
unittest.main() 
```

Testni bajaramiz va quyidagi natijani olamiz:

```aspnet
Ran 1 test in 0.001s

OK
```

Testimizni tahlil qilamiz. Dastaval biz obyektimiz to'g'ri yaratilayotganini tekshrish uchun `avto1` obyektini 3 ta prametr bilan yaratib oldik (`make, model, year`) va  bu xususiyatlar bo'sh emasligini  `assertIsNotNone()` metodi bilan tekshirdik.&#x20;

`avto1` obyektini yaratishda uning narhini ko'rsatmadik, demak bu xususiyat standart qiymat (`None`) ga teng bo'lishi kerak. Buni tekshirish uchun esa `assertIsNone()` metodiga murojat qildik. Vanihoyat, avtomobil kilometraji `0` ga teng ekanligini `assertEquals()` metodi yordamida test qildik.

Test so'ngida biz yana bir obyekt yaratdik (`avto2`) va bu safar avtomobil narhini ko'rsatganimiz uchun `assertEquals()` metodi yordamida bu qiymat to'g'ri saqlanganini tekshirib oldik.

Testlarni yozishni davom etamiz. Navbat obyektga tegishli turli metodlarga.

{% hint style="danger" %}
**Test dasturlarni alohida faylga yozishni unutmang.**
{% endhint %}

## `setUp()` METODI

Yuqoridagi misolda bitta test davomida 2 ta obyekt yaratdik, va obyektning parametrlarini qo'lda yangidan kiritdik. Agar shu yo'sinda davom etadigan bo'lsak, turli testlar uchun har gal yangi obyekt yaratishimiz, va ularning har biriga xususiyatlarni qayta-qayta kiritishimiz talab qilinadi. Buning oldini olish uchun test klassimizning boshida `setUp()` metodini yaratib, bu metod ichida barcha kerakli qiymatlarni va obyektlarni saqlab qo'yishimiz va turli testlarda shu qiymatlarga murojat qilishimiz mumkin:

```python
import unittest
from cars import Car

class CarTest(unittest.TestCase):
    """Car klassini tekshirish uchun test"""
    def setUp(self):        
        make = "GM"
        model = "Malibu"
        year = 2020        
        self.price = 40000
        self.km = 10000
        self.avto1 = Car(make,model,year)
        self.avto2 = Car(make,model,year,price=self.price)
        
    def test_create(self):                
        # Qiymatlar mavjudligini assertIsNotNone metodi bilan tekshiramiz
        self.assertIsNotNone(self.avto1.make)
        self.assertIsNotNone(self.avto1.model)
        self.assertIsNotNone(self.avto1.year)
        # Qiymat mavjud emasligini assertIsNone metodi bilan tekshiramiz
        self.assertIsNone(self.avto1.price)
        # Qiymat tengligini assertEquals metodi bilan tekshiramiz
        self.assertEqual(0,self.avto1.get_km())
        # avto2 narhini tekshiramiz
        self.assertEqual(self.price,self.avto2.price)

unittest.main()  
```

E'tibor bering, `setUp()` metodi ichida ba'zi o'zagruvchilar self yordamida berilgan (`self.price`,`self.km`, `self.avto1`, `self,avto2`). Bu o'zgaruvchilarga biz `CarTest()` klassining ichida istalgan joydan murojat qilishimiz mumkin. Shuning uchun ham, `test_create()` funksiyasi ichida biz yangi obyekt yaratmasdan, `setUp()` ichidagi `avto1` va `avto2` obyektlariga murojat qildik.

## METODLARNI TEKSHIRISH

Obyektimiz bir nechta metodlardan iborat. Ularning har biri uchun alohida test yozamiz. Bu metodlarni `CarTest` ichida yozishni unutmang.

Osonidan boshlaymiz:

```python
    def test_set_price(self):
        self.avto2.set_price(self.price)
        self.assertEqual(self.price,self.avto2.price)
```

Endi `add_km()` metodini tekshiraylik. Bu metodimiz faqatgina musbat qiymat qabul qilishi, manfiy qiymat uzatilganda `ValueError` xatosini qaytarishi kerak edi. Shuning uchun metodni test qilishda avval musbat, keyin esa manfiy qiymat berib ko'ramiz.

```python
    def test_add_km(self):
        #1 Musbat qiymat berib ko'ramiz
        self.avto1.add_km(self.km)
        self.assertEqual(self.km,self.avto1.get_km())
        #2 Manfiy qiymat berib ko'ramiz
        new_km = -5000        
        try:
            self.avto1.add_km(new_km)
        except ValueError as error:
            self.assertEqual(type(error), ValueError)
```

Navbat `get_info()` metodiga. Bu metod ham obyektning xususiyatlaridan kelib chiqqan holda 2 hil qiymat qaytarishi mumkin, demak testimiz bu ikki holatni hisobga olishi kerak.

```python
    def test_get_info(self):
        avto1_info = 'GM Malibu, 2020-yil, 0km yurgan.'
        self.assertEqual(avto1_info,self.avto1.get_info())
        # avto1 narhi va km o'zgartiramiz
        self.avto1.set_price(50000)
        self.avto1.add_km(20000)
        avto1_info = 'GM Malibu, 2020-yil, 20000km yurgan. Narhi: 50000'
        self.assertEqual(avto1_info,self.avto1.get_info())
```

Yakuniy test dasturimiz quyidagi ko'rinishga ega bo'ldi:

```python
import unittest
from cars import Car

class CarTest(unittest.TestCase):
    """Car klassini tekshirish uchun test"""
    def setUp(self):        
        make = "GM"
        model = "Malibu"
        year = 2020        
        self.price = 40000
        self.km = 10000
        self.avto1 = Car(make,model,year)
        self.avto2 = Car(make,model,year,price=self.price)
        
    def test_create(self):                
        # Qiymatlar mavjudligini assertIsNotNone metodi bilan tekshiramiz
        self.assertIsNotNone(self.avto1.make)
        self.assertIsNotNone(self.avto1.model)
        self.assertIsNotNone(self.avto1.year)
        # Qiymat mavjud emasligini assertIsNone metodi bilan tekshiramiz
        self.assertIsNone(self.avto1.price)
        # Qiymat tengligini assertEquals metodi bilan tekshiramiz
        self.assertEqual(0,self.avto1.get_km())
        # avto2 narhini tekshiramiz
        self.assertEqual(self.price,self.avto2.price)
    
    def test_set_price(self):
        self.avto2.set_price(self.price)
        self.assertEqual(self.price,self.avto2.price)
    
    def test_add_km(self):
        # Musbat qiymat berib ko'ramiz
        self.avto1.add_km(self.km)
        self.assertEqual(self.km,self.avto1.get_km())
        # Manfiy qiymat berib ko'ramiz
        new_km = -5000        
        try:
            self.avto1.add_km(new_km)
        except ValueError as error:
            self.assertEqual(type(error), ValueError)
    
    def test_get_info(self):
        avto1_info = 'GM Malibu, 2020-yil, 0km yurgan.'
        self.assertEqual(avto1_info,self.avto1.get_info())
        # avto1 narhi va km o'zgartiramiz
        self.avto1.set_price(50000)
        self.avto1.add_km(20000)
        avto1_info = 'GM Malibu, 2020-yil, 20000km yurgan. Narhi: 50000'
        self.assertEqual(avto1_info,self.avto1.get_info())

        
unittest.main()
```

Testni bajaramiz va quyidagi natijani olamiz:

```aspnet
....
----------------------------------------------------------------------
Ran 4 tests in 0.002s

OK
```

## AMALIYOT

* [30-darsimizda](https://python.sariq.dev/oop/30-vorislik-polimorfizm) `Shaxs` va `Talaba` klasslarini yaratgan edik. Shu ikki klassning xususiyatlari va metodlarini tekshiruvchi test dasturlar yozing.&#x20;
* Ikki klass uchun yagona test yoza olasizmi? (`isInstance()` funksiyasini eslang)

## KODLAR

{% embed url="<https://github.com/anvarnarz/python-darslar>" %}


---

# Agent Instructions: Querying This Documentation

If you need additional information that is not directly available in this page, you can query the documentation dynamically by asking a question.

Perform an HTTP GET request on the current page URL with the `ask` query parameter:

```
GET https://python.sariq.dev/testing/37-klass-test.md?ask=<question>
```

The question should be specific, self-contained, and written in natural language.
The response will contain a direct answer to the question and relevant excerpts and sources from the documentation.

Use this mechanism when the answer is not explicitly present in the current page, you need clarification or additional context, or you want to retrieve related documentation sections.
