# #28 KLASSLAR

{% embed url="<https://youtu.be/Mi0GzaBguEQ>" %}

## KIRISH

Avvalgi darsimizda ko'rganimizdek, klasslar Object oriented dasturlashning poydevorlaridan biridir. Klasslar bizga dasturlashga va dastur elementlariga real hayotdagi buyumlar (obyektlarga) yondoshgandek yondoshish imkonin beradi.

Klasslar, obyketlar va ularning qanday ishlashini tushungan dasturchi, mantiqiy fikrlashda ham kuchli bo'ladi. Mukammal va kompleks muammolarga ham yechimni ko'ra biladi.

## PYTHONDAGI KLASSLAR

Klass tushunchasi siz uchun yangi bo'lishi mumkin, lekin biz shu vaqtgacha ulardan doimiy ravishda foydalanib keldik.

Keling `x` o'zgaruvchi yaratamiz, unga biror qiymat yuklaymiz va `type()` funksiyasi yordamida uning turini kuramiz:

```python
x = 10
print(type(x))
```

Natija: `<class 'int'>`

```python
matn = "salom"
print(type(matn))
```

Natija: `<class 'str'>`

Yuqoridan ko'rayabmizki, `x` bu `int` klassidagi, `matn` esa `str` klassidagi obyektlar ekan. Demak biz o'zgaruvchi yaratganimizda, aslida Python `int` yoki `str` klassidan foydalangan holda yangi obyektlar yaratib kelayotgan ekan.

Huddi shu kabi, agar yangi funksiya yaratib, uning ham turini tekshirsak, funksiyamiz `function` klassiga tegishli obyekt bo'lib chiqadi.

```python
def salom_ber():
    print("Assalom alaykum")

print(type(salom_ber))
```

&#x20;Natija: `<class 'function'>`

Demak, Pythondagi har qanday o'zgaruvchi, funksiya va boshqa elementlar aslida obyektlar ekan.

### METODLAR

Har bir obyekt uning ustida bajarish mumkin bo'lgan funksiyalar bilan keladi. Bu funksiyalar obyekt ichida yashirin bo'ladi, va biz ularga nuqta va funksiya nomi orqali murojat qilishimiz mumkin. Bunday funksiyalar shu klass (yoki obyektga) tegishli **metodlar** deyiladi.

Biz ba'zi metodlar bilan avvalgi darslarimizda tanishdik. Bir klassga tegishli metodlar, boshqa klassdagi obyketlar uchun mavjud bo'lmasligi tabiiy. Misol uchun matnlar uchun mavjud metodlarni, butun yoki o'nli sonlarga qo'llab bo'lmaydi.

```python
matn = "salom"
print(matn.upper())
```

Natija: `SALOM`

```python
son = 20
print(son.lower())
```

Natija: **`AttributeError: 'int' object has no attribute 'lower'`**

Keling endi o'zimizning klasslarimizni yaratishni ko'ramiz.

## KLASS YARATISH

Yangi klass yaratish uchun class operatoridan foydalanamiz va klassimizga tushunarli nom beramiz. Esingizda bo'lsin, klass bu hali obyekt emas, bu obyekt uchun shablon. Shuning uchun klass yaratishda shu klassdagi obyektlar uchun umumiy bo'lgan xususiyatlar va funksiyalarni o'ylashimiz kerak.

Keling, Talaba degan klass yaratamiz:

```python
class Talaba:
    """Talaba nomli klass yaratamiz"""
    def __init__(self,ism,familiya,tyil):
        """Talabaning xususiyatlari"""
        self.ism = ism
        self.familiya = familiya
        self.tyil = tyil
```

Kodimizni tahlil qilamiz:

* `class Talaba` — `Talaba` nomli klass yaratdik. Klasslarga nom berishda uning birinchi harfini katta harfdan boshlash tavsiya qilinadi. Agar klass nomi 2 va undan ko'p so'zdan iborat bo'lsa har bir so'zni katta harf bilan boshlang.
* `def __init__(self)` — klassga tegishli xususiyatlarni saqlovchi maxsus metod (funksiya). self kalit so'zi ingliz tilidan "o'zi" deb tarjima qilinadi, va bu klassdan yaratilgan obyektning o'ziga ishora qiladi. Ya'ni keyinchalik biz obyekt ichidagi metodga murojat qilganimizda shu obyektning o'zi birinchi bo'lib funksiyaga argument sifatida uzatiladi, obyket ustida turli amallar bajarish imkonin beradi
* `def __init__(self,ism,familiya,tyil)` — yaratayotgan klassimizga xos xususiyatlarni `def __init__(self)` funksiyasiga argument sifatida uzatamiz. Bizning Talaba klassimiz ism, familiya va tug'ilgan yilga ega bo'ladi.&#x20;
* Keyingi qatorlarda esa `self.xususiyat = argument` komandasi yordamida uzatilgan argumentlarni klassning xususiyatlari bilan bo'glayapmiz. Bu yerda xususiyat nomi uzatilgan argument nomi bilan mos tushishi shart emas, unga istalgan nom berishimiz mumkin (masalan `self.name = ism`)

## KLASSDAN OBYEKT YARATAMIZ

Klassimiz tayyor, keling endi klassimizdan yangi obyekt yaratamiz.&#x20;

```python
talaba1 = Talaba("Alijon","Valiyev",2000)
```

Mana, `talaba1` obyektimiz tayyor. Obyektni yaratish uchun Talaba klassiga murojat qildik va talabaning ismi, familiyasi va tug'ilgan yilini parameter sifatida uzatdik.&#x20;

### OBYKETNING XUSUSIYATLARINI KO'RISH

Obyektning xususiyatlarini ko'rish uchun nuqta orqali murojat qilishimiz mumkin.

```python
print(talaba1.ism)
```

Natija: `Alijon`

```python
print(talaba1.familiya)
```

Natija: `Valiyev`

### KLASSDAN BIR NECHTA OBYEKTLAR YARATISH

Yuqoridagi klassdan biz istalgancha obyektlar yaratishimiz mumkin:

```python
talaba2 = Talaba("Olim","Olimov",1995)
talaba3 = Talaba("Husan","Akbarov",2004)
talaba4 = Talaba("Hasan","Akbarov",2004)
```

Bunda har bir obyekt o'zining alohida xususiyatlariga ega bo'ladi.

```python
print(talaba2.ism)
print(talaba4.familiya)
```

Natija:&#x20;

* `Olim`
* `Akbarov`

## KLASSGA METODLAR QO'SHAMIZ

Obyektimizning xususiyatlarini aniqlab oldik, keling endi obyekt bajarishi kerak bo'lgan metodlarni ham qo'shaylik.

```python
class Talaba:
    """Talaba nomli klass yaratamiz"""
    def __init__(self,ism,familiya,tyil):
        """Talabaning xususiyatlari"""
        self.ism = ism
        self.familiya = familiya
        self.tyil = tyil
    
    def tanishtir(self):
        print(f"Ismim {self.ism} {self.familiya}. {self.tyil} yilda tu'gilganman")
```

Boshlanishiga klassimizga bitta, `tanishtir` metodini qo'shdik. Bu metodimiz ko'rib turganingizdek bitta `self` (ya'ni obyektning o'zini) argumentini qabul qiladi va talaba haqidagi ma'lumotlarni konsolga chiqaradi.

### OBYEKTNING METODLARIGA MUROJAT QILAMIZ

Obyekt ichidagi funksiyaga ya'ni obyektning metodiga murojat qilamiz:

```python
talaba4 = Talaba("Hasan","Akbarov",2004)
talaba4.tanishtir()
```

Natija: `Ismim Hasan Akbarov. 2004 yilda tu'gilganman`

Klassimiz istalgancha metodlardan iborat bo'lishi mumkin:

```python
class Talaba:
    """Talaba nomli klass yaratamiz"""
    def __init__(self,ism,familiya,tyil):
        """Talabaning xususiyatlari"""
        self.ism = ism
        self.familiya = familiya
        self.tyil = tyil
    
    def get_name(self):
        """Talabaning ismini qaytaradi"""
        return self.ism
    
    def get_lastname(self):
        """Talabaning familiyasini qaytaradi"""
        return self.familiya
    
    def get_fullname(self):
        """Talabaning ism-familiyasini qaytaradi"""
        return f"{self.ism} {self.familiya}"
    
    def tanishtir(self):
        print(f"Ismim {self.ism} {self.familiya}. {self.tyil} yilda tu'gilganman")
```

```python
talaba1 = Talaba("Alijon","Valiyev",2000)
print(talaba1.get_fullname())
```

Natija: `Alijon Valiyev`

### ARGUMENT QABUL QILUVCHI METODLAR

Yuqoridagi misolimizda barcha metodlar faqatgina self parametrini qabul qilishayapti. Aslida, barcha funksiyalar kabi, klass ichidagi obyektlarni ham boshqa argumentlar qabul qiladigan qilib yozish mumkin.

```python
class Talaba:
    """Talaba nomli klass yaratamiz"""
    def __init__(self,ism,familiya,tyil):
        """Talabaning xususiyatlari"""
        self.ism = ism
        self.familiya = familiya
        self.tyil = tyil
    
    def get_name(self):
        """Talabaning ismini qaytaradi"""
        return self.ism
    
    def get_lastname(self):
        """Talabaning familiyasini qaytaradi"""
        return self.familiya
    
    def get_fullname(self):
        """Talabaning ism-familiyasini qaytaradi"""
        return f"{self.ism} {self.familiya}"
    
    def get_age(self,yil):
        """Talabaning yoshini qaytaradi"""
        return yil-self.tyil
    
    def tanishtir(self):
        print(f"Ismim {self.ism} {self.familiya}. {self.tyil} yilda tu'gilganman")
```

Yuqorida klassimizga yangi `get_age(self,yil)` metodini qo'shdik. Bu metod obyektning o'zidan tashqari, qo'shimcha, `yil` argumentini ham qabul qiladi va talabaning yoshini qaytaradi.

```python
talaba1 = Talaba("Alijon","Valiyev",2000)
print(talaba1.get_age(2021))
```

Natija: `21`

## `pass` OPERATORI

Pythonda hech qanday vazifani bajarmaydigan `pass` operatori mavjud. Bu operatordan bo'sh metodlar yaratishda foydalanish mumkin. Misol uchun siz klassingiz uchun muhim metodlarni bilasiz, lekin metod badani hali tayyor emas. Agar metod badanini bo'sh qoldirsangiz, Python **`IndentationError`** xatosini qaytaradi. Shunday xolatlarda, funksiya badaniga `pass` operatorini qo'yib ketishimiz mumkin:

```python
class User:
    def __int__(self,name,username,email):
        self.name = name
        self.uname = username
        self.mail = email
    
    def describe():
        pass
    
    def get_email():
        pass
```

&#x20;Yuqoridagi klassimizda `describe()` va `get_email()` funksiyalar badani hali tayyor emas, bo'shliqni to'ldirish uchun esa pass operatoridan foydalanganmiz.

{% hint style="info" %}
`pass` operatoridan `if-else`, `for`, `while` operatorlari badanida ham foydalanish mumkin.
{% endhint %}

## AMALIYOT

* Web sahifangiz uchun foydalanuvchi (user) klassini tuzing. Klassning xususiyatlari sifatida odatda ijtimoiy tarmoqlar talab qiladigan ma'lumotlarni kiriting (ism, foydalanuvchi ismi, email, va hokazo)
* Klassga bir nechta metodlar qo'shing, jumladan get\_info() metodi foydalanuvchi haqida yig'ilgan ma'lumotlarni chiroyli qilib chiqarsin (masalan: "Foydalanuvchi: alijon1994, ismi: Alijon Valiyev, email: <alijon1994@gmail.com>).
* Klassdan bir nechta obyektlar yarating va uning xususiyatlari va metodlariga murojat qiling.

