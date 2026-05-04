# # 36 FUNKSIYANI TEKSHIRISH

<Embed url="https://youtu.be/GgAs_VhWucY" />

## KIRISH

Dastur davomida yangi funksiya yoki klass yozar ekanmiz, ularni to'g'ri ishlashini ham tekshirishimiz tabiiy. Kodni tekshirish, kelajakda dasturimiz xato ishlashining oldini oladi. Odatda, funksiya va klasslarni tekshirish uchun alohida test dasturlar yozishimiz mumkin. Bunday dasturlar funksiyaga turli parametrlar orqali murojat qilib, undan qaytgan qiymatlar to'g'ri yoki xato ekanini tekshiradi.

Pythonda bu jarayonni osonlashtirish uchun maxsus `unittest` moduli mavjud. `unittest` yordamida alohida funksiya, obyekt yoki butun boshli modulni ham tekshirshimiz mumkin. Lekin, tavsiya qilingan usuli bu testni dastavval kichik qismlardan boshlab, kengaytirib borish.

## FUNKSIYANI TEKSHIRISH

Boshlanishiga biror sodda funksiya yozamiz. Quyidagi funksiya foydalanuvchi ismi va familiyasini qabul qiladi, va ism familiyani jamlab qaytaradi:

```python
def get_full_name(ism, familiya):
    return f"{ism} {familiya}".title()
```

Funksiyani tekshiramiz:

```python
>>> print(get_full_name('alijon','valiyev'))
'Alijon Valiyev'
```

Keling endi shu funksiyamizni tekshirish uchun dastur yozamiz. Bu yerda ikki narsaga ahamiyat beramiz: avvalo funksiyamizni alohida modulda saqlaymiz (`name.py`), ikkinchidan test dasturimizni ham alohida modulda yozamiz va unga ham tushunarli nom beramiz (masalan, `name_test.py`).

Test faylimizning (`name_test.py`) tarkibi quyidagicha bo'ladi:

```python
import unittest
from name import get_full_name

class NameTest(unittest.TestCase):
    def test_toliq_ism(self):
        formatted_name = get_full_name('alijon','valiyev')        
        self.assertEqual(formatted_name, 'Alijon Valiyev')

unittest.main()
```

Dasturni tahlil qilamiz:

- Dastavval unittest modulini chaqiramiz (`import unittest`)
- Keyingi qatorda `name.py` modulimizdan tekshirmoqchi bo'lgan funksiyamizni ham yuklab olamiz (`get_full_name`).
- 4-qatorda test klassini yaratamiz, bu klass`unittest.TestCase` klassidan meros oladi. Bu klass berilgan parametrlar uchun funksiyadan qaytgan qiymatlarni tekshirishga mo'ljallangan. Klassimizga o'zimiz istagan, tushunarli nom beramiz (`NameTest`).
- Klassimiz ichida `test_toliq_ism` metodini yaratdik. Bu metod `get_full_name` funksiyasidan qaytgan qiymatni biz avvaldan bergan qiymatga teng yoki yo'q ekanini tekshiradi. Buning uchun esa maxsus `.assertEqual()` metodidan foydalandik. E'tibor bering, test medotlarning nomi har doim `test` so'zi bilan boshlanishi kerak.
- `assertEqual()` metodi ikki qiymat qabul qiladi va ularning teng ekanligini tekshiradi (assert ingliz tilidan tasdiqlash deb tarjima qilinadi). Agar `get_full_name('alijon','valiyev')` funksiyamiz to'g'ri ishlasa, funksiyadan `'Alijon Valiyev'` qiymati qaytishi kerak. `assertEqual()` metodi aynan shuni tekshirishga mo'ljallangan.
- So'nggi qatorda unittest klassinini chaqiramiz, bu esa o'z navbatida biz yuqorida yozgan testni chaqiradi.

`name_test.py` dasturimizni bajaramiz va quyidagi natijani olamiz:

```aspnet
Ran 1 test in 0.001s

OK
```

Natijadan bitta test bajarilganini va va bu test muvaffaqiyatli o'tganini (`OK`) ko'rishimiz mumkin.

Keling endi dars boshida yaratilgan `get_full_name` funksiyamizga o'zgartirish kiritamiz:

```python
def get_full_name(ism, familiya, otasi=''):
    if otasi:
        return f"{ism} {otasi} {familiya}"   
    else:
        return f"{ism} {familiya}".title()
```

Bu safar funksiyamiz otasining ismini ham qabul qiladi, lekin bu argument ixtiyoriy.

Testimizga ham o'zgartirish kiritamiz. Bu safar ikki hil ism uchun ikkita alohida test bajaramiz:

```python
import unittest
from name import get_full_name

class NameTest(unittest.TestCase):
    def test_toliq_ism(self):
        formatted_name = get_full_name('alijon','valiyev')        
        self.assertEqual(formatted_name, 'Alijon Valiyev')
    def test_toliq_ism_otasi(self):
        name = get_full_name('hasan','husanov','olimovich')
        self.assertEqual(name,'Hasan Olimovich Husanov')

unittest.main()
```

Testni bajaramiz, va quyidagi natijani olamiz:

```aspnet
AssertionError: 'hasan olimovich husanov' != 'Hasan Olimovich Husanov'
- hasan olimovich husanov
? ^     ^         ^
+ Hasan Olimovich Husanov
? ^     ^         ^


----------------------------------------------------------------------
Ran 2 tests in 0.001s

FAILED (failures=1)
```

Bu safar funksiyamiz 1 ta testdan yiqildi (`failures=1`). Biz kutgan natija (Hasan Olimovich Husanov) va funksiya qaytargan natija (hasan olimovich husanov) bir hil emas. Ya'ni, ism familiya va otasining ismi katta harflar bilan yozlishi kerak edi, lekin natija unday emas. Demak funksiyamizda xato bor. Xatoni to'g'rilaymiz:

```python
def get_full_name(ism, familiya, otasi=''):
    if otasi:
        return f"{ism} {otasi} {familiya}".title()   
    else:
        return f"{ism} {familiya}".title()
```

Testni qaytadan chaqiramiz:

```aspnet
Ran 2 tests in 0.001s

OK
```

Bu safar funksiyamiz  ikki testdan ham muvaffaqiyatli o'tdi.

## SONLARNI TEKSHIRISH

Yuqorida matn qaytaruvchi funksiyani tekshirishni ko'rdik. Keling endi sonlar bilan ishlashni ko'ramiz. Misol tariqasida yangi `circle.py` modulini yaratamiz va uning ichida doiraning yuzini ( $$\pi r^2$$ ) va perimetrini ( $$2\pi r$$)  hisoblaydigan funksiyalar yozamiz:

```python
def getArea(r,pi=3.14159):
    """Doiraning yuzini qaytaruvchi funksiya"""
    return pi*(r**2)

def getPerimeter(r,pi=3.14159):
    """Doiraning perimetrini qaytaruvchi funksiya"""
    return 2*pi*r
```

E'tibor bering, ikki funksiya ham, agar foydalanuvchi aniq qiymat bermasa, $$\pi$$ ning qiymatini standart argument sifatida `3.14159` ga teng deb qabul qilayapti. Ushbu funksiyalarni tekshirish uchun alohida `circle_test.py` test dasturini yozamiz. Matnlardan farqli ravishda, sonlarni taqqoslash uchun `assertAlmostEqual()` metodidan foydalanamiz. Bu metod, ikki sonni nuqtadan keyin 7 xonagacha aniqlikda tekshiradi:

```python
import unittest
from circle import getArea, getPerimeter

class CircleTest(unittest.TestCase):
    def test_area(self):
        self.assertAlmostEqual(getArea(10), 314.159)
        self.assertAlmostEqual(getArea(3),28.27431)
    def test_perimeter(self):
        self.assertAlmostEqual(getPerimeter(10), 62.8318)
        self.assertAlmostEqual(getPerimeter(4), 25.13272)
        
unittest.main())
```

Bu yerda e'tibor qiling, biz har bir funksiya uchun 2 tadan test yozdik. Testni bajaramiz va quyidagi natijani olamiz:

```aspnet
Ran 2 tests in 0.001s

OK
```

## MANTIQIY QIYMATLARNI TEKSHIRISH

Agar funksiya mantiqiy qiymat qaytarsa, bunday funksiyalarni `assertTrue()` va `assertFalse()` metodlari yordamida tekshirishimiz mumkin.

Quyidagi funksiyamiz kiritilgan son tub yoki yo'q ekanini tekshiradi:

```python
def tubSonmi(n):
    if n==2 or n==3: return True
    if n%2==0 or n&lt;2: return False
    for i in range(3, int(n**0.5)+1, 2):   # faqat toq sonlarni tekshiramiz
        if n%i==0:
            return False   
    return True
```

Funksiyani alohida `tubSonmi.py` fayliga saqlaymiz. Funksiyani tekshirish uchun `tubSon_test.py` dasturini yozamiz:

```python
import unittest
from tubSonmi import tubSonmi

class tubSonTest(unittest.TestCase):
    def test_true(self):
        self.assertTrue(tubSonmi(7))
        self.assertTrue(tubSonmi(193))
        self.assertTrue(tubSonmi(547))
    def test_false(self):
        self.assertFalse(tubSonmi(6))
        self.assertFalse(tubSonmi(265))
        self.assertFalse(tubSonmi(489))
        
unittest.main()
```

Test davomida `tubSonmi()` funksiyasini bir nechta tub (`7, 193, 547`) va tub bo'lmagan (`6, 265, 489`) sonlar bilan chaqirdik. Bunda `assertTrue()` metodi funksiyamiz haqiqatdan ham `True` qiymatini qaytarishini, `assertFalse()` metodi esa funksiyamiz `False` qiymat qaytarishini tekshiradi.

## TAQQOSLASH METODLARI

`TestCase` klassi tarkibidagi boshqa taqqoslash metodlari ham mavjud:

| Metod                                                                                                                | Nimani taqqoslaydi?          |
| -------------------------------------------------------------------------------------------------------------------- | ---------------------------- |
| [`assertEqual(a, b)`](https://docs.python.org/3/library/unittest.html#unittest.TestCase.assertEqual)                 | `a == b`                     |
| [`assertNotEqual(a, b)`](https://docs.python.org/3/library/unittest.html#unittest.TestCase.assertNotEqual)           | `a != b`                     |
| [`assertTrue(x)`](https://docs.python.org/3/library/unittest.html#unittest.TestCase.assertTrue)                      | `x` ning qiymati `True`      |
| [`assertFalse(x)`](https://docs.python.org/3/library/unittest.html#unittest.TestCase.assertFalse)                    | `x` ning qiymati `False`     |
| [`assertIs(a, b)`](https://docs.python.org/3/library/unittest.html#unittest.TestCase.assertIs)                       | `a` bu `b`                   |
| [`assertIsNot(a, b)`](https://docs.python.org/3/library/unittest.html#unittest.TestCase.assertIsNot)                 | `a` bu `b` emas              |
| [`assertIsNone(x)`](https://docs.python.org/3/library/unittest.html#unittest.TestCase.assertIsNone)                  | `x` ning qiymati `None`      |
| [`assertIsNotNone(x)`](https://docs.python.org/3/library/unittest.html#unittest.TestCase.assertIsNotNone)            | `x` ning qiymati `None` emas |
| [`assertIn(a, b)`](https://docs.python.org/3/library/unittest.html#unittest.TestCase.assertIn)                       | `a` `b` ning ichida          |
| [`assertNotIn(a, b)`](https://docs.python.org/3/library/unittest.html#unittest.TestCase.assertNotIn)                 | `a` `b` ning ichida emas     |
| [`assertIsInstance(a, b)`](https://docs.python.org/3/library/unittest.html#unittest.TestCase.assertIsInstance)       | `a` `b` ning vorisi          |
| [`assertNotIsInstance(a, b)`](https://docs.python.org/3/library/unittest.html#unittest.TestCase.assertNotIsInstance) | `a` `b` ning vorisi emas     |

## AMALIYOT

Quyidagi funksiyalarni yarating, va **ularning har biri uchun test dasturlarini yozing**:

- Uchta son qabul qilib, ulardan eng kattasini qaytaruvchi funksiya
- Matnlardan iborat ro'yxat qabul qilib, ro'yxatdagi har bir matnning birinchi harfini katta harfga o'zgatiruvchi funksiya
- Berilgan sonlar ro'yxatidan juft sonlarni ajratib oluvchi funksiya
- Berilgan son [Fibonachchi ketma-ketligida](https://medium.com/@qudratxoja.musayev/fibonachchi-sonlari-va-u-haqida-qiziqarli-faktlar-47000a80264d) uchraydimi (`True`) yoki yo'q (`False`) qaytaruvchi funksiya yozing.

## KODLAR

<Embed url="https://github.com/anvarnarz/python-darslar" />
