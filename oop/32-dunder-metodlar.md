# #32 DUNDER METODLAR

{% embed url="<https://youtu.be/KOKEsau2uaU>" %}

## MAXSUS METODLAR

Pythonda obyektlar bilan ishlashni yanada qulay qilish uchun bir nechta maxsus metodlar bor. Bu metodlarning nomi ikki pastki chiziq bilan yozilgani uchun, **d**ouble **under**score yoki qisqa qilib dunder metodlar deb ataladi. Dunder metolar yordamida obyektlarga qo'shimcha qulayliklar va vazifalar qo'shishimiz mumkin. Klass yoki obyektga oid dunder metodlar ro'yxatini ko'rish uchun dir() funksiyasidan foydalanamiz:

```python
>>> dir(Avto)
['_Avto__num_avto',
 '__class__',
 '__delattr__',
 '__dict__',
 '__dir__',
 '__doc__',
 '__eq__',
 '__format__',
 '__ge__',
 '__getattribute__',
 '__gt__',
 '__hash__',
 '__init__',
 '__init_subclass__',
 '__le__',
 '__lt__',
 '__module__',
 '__ne__',
 '__new__',
 '__reduce__',
 '__reduce_ex__',
 '__repr__',
 '__setattr__',
 '__sizeof__',
 '__str__',
 '__subclasshook__',
 '__weakref__',
 'make',
 'model',
 'narh',
 'rang',
 'yil']
```

Dunder metodlardan biz `__init__` metodi bilan tanishdik. Bu metod klassdan obyekt yaratishda chaqiriladi va obyektning xususiyatlarini belgilaydi. Ushbu darsimizda esa maxsus metodlarning ba'zilari bilan tanishamiz.

## OBYEKT HAQIDA MA'LUMOT

Obyektga `print()` yoki `str()` orqali murojat qilinganda obyekt haqida tushunarli ma'lumot qaytarish uchun `__repr__`va `__str__` metodlaridan foydalanamiz. Tushunarli bo'lishi uchun avvalgi darsimizdagi `Avto` klassiga qaytamiz:

```python
class Avto:
    __num_avto = 0
    """Avtomobil klassi"""
    def __init__(self,make,model,rang,yil,narh):
        """Avtomobilning xususiyatlari"""
        self.make = make
        self.model = model
        self.rang = rang
        self.yil = yil
        self.narh = narh
        Avto.__num_avto += 1
```

Yuqoridagi klassdan yangi obyekt yaratamiz va obyekt haqida ma'lumot olish uchun `print()` funksiyasini chaqiramiz:

```python
avto1 = Avto("GM","Malibu","Qora",2020,40000)
print(avto1) # obyekt haqida ma'lumot
```

Natija: `<__main__.Avto object at 0x00000238A6DAE0C8>`&#x20;

Qandaydur tushunarsiz ma'lumot. Ekrandagi natijadan biz faqat `avto1` obyektimiz `Avto` klassiga tegishli ekanini ko'ramiz. Qanday qilib shuning o'rniga obyekt haqida tushunarliroq ma'lumot olishimiz mumkin?

Gap shundaki biz har gal obyketga `print()` (yoki `str()` yoki `repr()`) orqali murojat qilganimizda, Python obyket ichida `__str__` yoki `__repr__` metodlariga murojat qiladi. Agar biz bu metodlarni yozmagan bo'lsak, yuqoridagi kabi umumiy ma'lumot qayataradi.&#x20;

Biz ushbu metodlarni yangidan yozib, biz istagan ma'lumotni qayataradian qilishimiz mumkin. Odatda, yuqoridagi ikki metoddan birini yozish kifoya. Odatda, `__repr__` umumiyorq, `__str__` esa batafsilroq ma'lumot olish uchun ishlatiladi.&#x20;

Ikkalasidan birini tanlaganda, `__repr__`metodiga yon bosiladi, sababi bu metod `print()`, `str()` va `repr()` funksiyalarining hammasi bilan ishlaydi. Keling biz ham yuoqirdagi klassimizga`__repr__`metodini qo'shamiz:

```python
class Avto:
    __num_avto = 0
    """Avtomobil klassi"""
    def __init__(self,make,model,rang,yil,narh):
        """Avtomobilning xususiyatlari"""
        self.make = make
        self.model = model
        self.rang = rang
        self.yil = yil
        self.narh = narh
        Avto.__num_avto += 1
    
    def __repr__(self):
        """Obyekt haqida ma'lumot"""
        return f"Avto: {self.rang} {self.make} {self.model}"
```

Qaytadan `print()` funksiyasini chaqiramiz:

```python
avto1 = Avto("GM","Malibu","Qora",2020,40000)
print(avto1)
```

Natija: `Avto: Qora GM Malibu`

Mana endi natijamiz ancha tushunarli ko'rinishda chiqdi.

## OBYEKTLARNI TAQQOSLASH

Taqqoslash operatorlari yordamida biz turli obyektlarni solishtirishimiz mumkin. Taqqoslash natijasi mantiqiy qiymat (`True` yoki `False`) ko'rinishida bo'ladi.&#x20;

```python
x,y = 5,10
print(x>y)
```

Natija: `False`

Keling endi Avto klassidan 2 ta obyekt yaratamiz, va ularni taqqoslab ko'ramiz:

```python
avto1 = Avto("GM","Malibu","Qora",2020,40000)
avto2 = Avto("GM","Lacetti","Oq",2020,20000)
avto1>avto2
```

Natija: `TypeError: '>' not supported between instances of 'Avto' and 'Avto'`

Xatolik. Demak bu ikki obyektni solshtirib bo'lmas ekan.&#x20;

Biz taqqolash operatorlariga murojat qilganimizda, Python obyektlar ichida taqqoslash uchun maxsus metodlarni qidiradi, agar metodlar topilmasa yuqoridagi kabi `TypeError` qaytaradi.&#x20;

Taqqoslash metodlari quyidagilardan iborat:

| Metod              | Operator |
| ------------------ | -------- |
| `x.__lt__(self,y)` | `x<y`    |
| `x.__le__(self,y)` | `x<=y`   |
| `x.__gt__(self,y)` | `x>y`    |
| `x.__ge__(self,y)` | `x>=y`   |
| `x.__eq__(self,y)` | `x==y`   |
| `x.__ne__(self,y)` | `x!=y`   |

Yuqoridagi obyektlardan yarmi uchun metodlar yozishimiz kifoya, misol uchun `__lt__` (x\<y) metodini yozsak, `__gt__` (x>y) metodini yozishimiz shart emas, yoki `__le__` metodi, `__ge__`metodini ham o'z ichiga oladi, va hokazo.

Keling tushunarli bo'lishi uchun Avto klassiga obyektlarni solishtirish uchun metod yozamiz. Deylik, biz obyektlarni **narhi** bo'yicha solishtirmoqchimiz, unda klassimizga quyidagi metodlarni qo'shamiz (klassni to'liq yozmadik, faqat qo'shilgan metodlarni keltiramiz):

```python
    def __eq__(self,boshqa_avto):
        """Tenglik"""
        return self.narh == boshqa_avto.narh
    
    def __lt__(self,boshqa_avto):
        """Kichik"""
        return self.narh<boshqa_avto.narh
    
    def __le__(self,boshqa_avto):
        """Kichik yoki teng"""
        return self.narh<=boshqa_avto.narh
```

Kodimizga e'tibor qilsangiz biz tenglik (`__eq__`) yoki kichiklikni (`__lt__`) tekshirmoqchi bo'lganimizda ikki avtoning aynan narhi bo'yicha solishtiramiz (`self.narh == boshqa_avto.narh`).

Mana endi avtolarni solishtirsak bo'ladi:

```python
avto1 = Avto("GM","Malibu","Qora",2020,40000)
avto2 = Avto("GM","Lacetti","Oq",2020,20000)
print(avto1>avto2)
```

Natija: `False`

```python
avto3 = Avto("Honda","Accord","Oq",2017,40000)
print(avto1==avto3)
```

Natija: `True`

## OBYEKT UZUNLIGI

Pythonda `len()` funksiyasi yordamida turli obyektlarning uzunligini bilishimiz mumkin, misol uchun matn, ro'yxat, lug'at, set va hokazo.

```python
matn = 'hello world'
print(len(matn))
```

Natija: `11`

```python
sonlar = [12, 34, 56, 66]
print(len(sonlar))
```

Natija: `4`

Biz len() funksiyasiga murojat qilganimizda, Python funksiyaga uzatilgan obyektning ichidagi maxsus `__len__` metodiga murojat qiladi. Agar bu metod mavjud bo'lmasa dasturimiz xato qaytaradi.

```python
len(avto1)
```

Natija: `TypeError: object of type 'Avto' has no len()`

Misol uchun, bizning Avto klassimizda bu metod yozilmagan, shuning uchun Python TypeError xatosini qaytardi.

Kelin endi `__len__`metodini qanday ishlatishga ham misol ko'raylik.

Boshlanishiga, yangi, `AvtoSalon` degan klass yaratamiz. Bu klassimiz 2 ta xususiyatga ega: salon nomi (`name`) va salondagi mashinalar (`avtolar`).

```python
class AvtoSalon:
    """Avtosalon klassi"""
    def __init__(self,name):
        self.name = name
        self.avtolar = []

    def __repr__(self):
        return f"{self.name} avtosaloni"
```

Yuqoridagi klassdan yangi obyekt yaratamiz:

```python
salon1 = AvtoSalon("MaxAvto")
print(salon1)
```

Natija: MaxAvto avtosaloni

`AvtoSalon` klassimizga `__repr__`metodini qo'shganimiz uchun natijamiz chiroyli ko'rinishda chiqdi.

Keling endi salonga avtomobil qo'shish uchun yangi `add_avto()` metodini yozamiz. Bu metodimiz Avto klassiga oid obyektlarni qabul qilishi kerak. `add_avto()` ga uaztilgan parametr Avto klassiga tegishli yoki yo'qligini tekshirish uchun maxsus `isinstance()` funksiyasidan foydalanamiz.

Bu funksiya biror obyekt ma'lum klassga tegishli ekanligini tekshirish uchun ishlatiladi:

```python
>>> isinstance("salom",str)
True # "salom" bu str
>>> isinstance(9.5,int)
False # 9.5 int (butun son) emas
>>> isinstance(avto1,Avto)
True # avto1 Avto klassiga tegishli
```

`add_avto()` metodiga qaytamiz:

```python
class AvtoSalon:
    """Avtosalon klassi"""
    def __init__(self,name):
        self.name = name
        self.avtolar = []

    def __repr__(self):
        return f"{self.name} avtosaloni"
    
    def add_avto(self,avto):
        if isinstance(avto,Avto): # agar avto Avto klassidan bo'lsa
            self.avtolar.append(avto)
        else:
            print("Avto obyketini kiriting")
```

Metodimizni tekshirib ko'ramiz:

```python
# Avto obyektlarini yaratamiz
avto1 = Avto("GM","Malibu","Qora",2020,40000)
avto2 = Avto("GM","Lacetti","Oq",2020,20000)
avto3 = Avto("Toyota",'Carolla',"Silver",2018, 45000)

# Yuqoridagi obyektlarni salon1 ga qo'shamiz
for avto in [avto1, avto2, avto3]: 
    salon1.add_avto(avto)
```

Mana navbat `__len__` metodiga. Biz bu metod yordamida `len()` funksiyasi salonimizdagi avtomobillar sonini qaytaradigan qilamiz. Buning uchun yuqoridagi `AvtoSalon` klassiga `__len__` funksiyani ham qo'shamiz va uni obyekt ichidagi avtolar ro'yxatyining uzunligini qaytaradigan qilamiz:

```python
    def __len__(self):
        return len(self.avtolar)
```

Mana endi bizning `AvtoSalon` klassimizga oid obyektlar uchun ham `len()` funksiyasini qo'llasak bo'ladi:

```python
>>> print(len(salon1))
3 # Salonimizda 3 ta moshina bor
```

## OBYEKT ELEMENTLARIGA MUROJAT QILISH

Ba'zi obyektlarning (matn, ro'yxat, lug'at va hokazo) elementlariga alohida murojat qilish mumkin.&#x20;

```python
>>> mevalar = ['olma','anor','uzum']
>>> mevalar[0]
'olma'
```

Bizning salonimizda ham 3 ta avto bor, ularni ko'rish uchun yuqoridagi kabi element raqami orqali murojat qila olamizmi?

```python
salon1[0]
```

Natija: `TypeError: 'AvtoSalon' object is not subscriptable`

Afsuski yo'q. Ko'rib turganingizdek bizning obyektimizga bunday murojat qilib bo'lmas ekan. Obyektimizga bu xususiyatni qo'shish uchun `__getitem__`metodini yozishimiz kerak.

```python
class AvtoSalon:
    """Avtosalon klassi"""
    def __init__(self,name):
        self.name = name
        self.avtolar = []

    def __repr__(self):
        return f"{self.name} avtosaloni"
    
    def __len__(self):
        return len(self.avtolar)
    
    def __getitem__(self,index):
        return self.avtolar[index]
```

Endi `salon1` obyektimizning elementlariga murojat qilinganda `__getitem__`metodi obyekt ichidagi `avtolar` ro'yxatidan ko'rsatilgan element (avtomobilni) qaytaradi.

```python
>>> salon1[0]
Avto: Qora GM Malibu
>>> salon1[1]
Avto: Oq GM Lacetti
>>> salon1[2]
Avto: Silver Toyota Carolla
>>> salon1[:] # barcha elementlarni ko'rish
[Avto: Qora GM Malibu, Avto: Oq GM Lacetti, Avto: Silver Toyota Carolla]
```

Keling obyekt elementlaridan birini o'zgartirib ko'ramiz:

```python
avto4 = Avto("Mazda", "6", 'Qizil',2015,35000)
salon1[0]=avto4
```

Natija: `TypeError: 'AvtoSalon' object does not support item assignment`

Yana xatolik. Gap shundaki `__getitem__` metodi o'z nomi bilan (get) element qaytaruvchi metod. Biror elementni o'zgartirish uchun esa `__setitem__`metodini ham qo'shishimiz kerak. Bu metodimizga murojat qilinganda ham, yangi qiymat Avto klassiga oid ekanligini tekshirib olish maqsadga muvofiq bo'ladi:

```python
    def __setitem__(self,index,value):
        if isinstance(value,Avto):
            self.avtolar[index]=value
```

Qaytadan elementni o'zgartirishga harakat qilib ko'ramiz:

```python
avto4 = Avto("Mazda", "6", 'Qizil',2015,35000)
salon1[0]=avto4
print(salon1[0])
```

Natija: `Avto: Qizil Mazda 6`

Kutilgan natija chiqdi

## OPERATORLARNI QAYTA TALQIN QILISH (OVERLOADING)

Pythonda obyektlar o'rtasida turli arifmetik amallarni bajarish mumkin va bu amallar obyektning turiga qarab, Pytnon tomonidan turlicha talqin qilinadi. Masalan:

Sonlar:

```python
>>> x,y=10,20
>>> x+y
30
>>> x*5
50
```

Matnlar:

```python
>>> t1 = "hello"
>>> t2 = "world"
>>> t1+t2
'helloworld'
>>> t1*5
'hellohellohellohellohello'
```

Ro'yxatlar:

```python
>>> l1 = [1, 2, 3]
>>> l2 = [4, 5, 6]
>>> l1+l2
[1, 2, 3, 4, 5, 6]
>>> l1*2
[1, 2, 3, 1, 2, 3]
```

va hokazo.

Keling, bu amallarni bizning obyektimizga ham qo'llab ko'ramiz. Boshlanishiga 2 ta avtosalon yarataylik, va har biriga alohida avtolar qo'shaylik. Ishimizni osonlashtirish uchun `add_avto()` metodimizni ham istalgancha parametr qabul qilishga moslab o'zgartiramiz:

```python
class AvtoSalon:
    """Avtosalon klassi"""
    def __init__(self,name):
        self.name = name
        self.avtolar = []

    def __repr__(self):
        return f"{self.name} avtosaloni"
    
    def __len__(self):
        return len(self.avtolar)

    def __getitem__(self,index):
        return self.avtolar[index]
    
    def __setitem__(self,index,value):
        if isinstance(value,Avto):
            self.avtolar[index]=value
    
    def add_avto(self,*qiymat):
        for avto in qiymat: 
            if isinstance(avto,Avto):
                self.avtolar.append(avto)
            else:
                print("Avto obyketini kiriting")
```

Obyektlarni yaratamiz:

```python
salon1 = AvtoSalon("MaxAvto")
salon2 = AvtoSalon("Avto Lider")
```

```python
avto1 = Avto("GM","Malibu","Qora",2020,40000)
avto2 = Avto("GM","Lacetti","Oq",2020,20000)
avto3 = Avto("Toyota",'Carolla',"Silver",2018, 45000)
avto4 = Avto("Mazda", "6", 'Qizil',2015,35000)
avto5 = Avto("Volkswagen","Polo",'Qora',2015,30000)
avto6 = Avto("Honda","Accord","Oq",2017,42000)
```

```python
salon1.add_avto(avto1, avto2, avto3)
salon2.add_avto(avto4, avto5, avto6)
```

Mavzuga qaytamiz. Operatorlarni qayta talqin qilish. Keling boshlanishiga ikki obyektni qo'shib ko'ramiz:

```python
salon1+salon2
```

Natija: `TypeError: unsupported operand type(s) for +: 'AvtoSalon' and 'AvtoSalon'`

Demak, bu ikki obyektni qo'shib bo'lmas ekan. Biz obyekt egasi sifatida qo'shish operatorini o'zimiz istagancha talqin qilishimiz mumkin. Misol uchun AvtoSalon obyektiga boshqa AvtoSalon obyektini qo'shganda, yangi AvtoSalon obyektini qaytaraylik va bu yangi obyekt avvalgi ikki obyektning avtolariga ega bo'lsin.&#x20;

Qo'shish operatorini qayta talqin qilish uchun AvtoSalon klassimizga `__add__` metodini qo'shamiz.

```python
    def __add__(self,qiymat):
        if isinstance(qiymat,AvtoSalon):
            yangi_salon =  AvtoSalon(f"{self.name} {qiymat.name}")
            yangi_salon.avtolar = self.avtolar + qiymat.avtolar
            return yangi_salon
```

Qo'shish operatorini tekshirib ko'ramiz:

```python
>>> salon3 = salon1+salon2
>>> print(salon3)
MaxAvto Avto Lider avtosaloni
>>> salon3[:]
[Avto: Qora GM Malibu,
 Avto: Oq GM Lacetti,
 Avto: Silver Toyota Carolla,
 Avto: Qizil Mazda 6,
 Avto: Qora Volkswagen Polo,
 Avto: Oq Honda Accord]
```

Istasak, qo'shish operatori yordamida salonga yangi Avto qo'shish imkoniyatini ham yaratishimiz mumkin:

```python
    def __add__(self,qiymat):
        if isinstance(qiymat,AvtoSalon):
            yangi_salon =  AvtoSalon(f"{self.name} {qiymat.name}")
            yangi_salon.avtolar = self.avtolar + qiymat.avtolar
            return yangi_salon
        elif isinstance(qiymat,Avto):
            self.add_avto(qiymat)
        else:
            print(f"AvtoSalon ga {type(qiymat)} qo`shib bo`lmaydi")
```

Tekshirib ko'ramiz:

```python
avto7 = Avto("BMW", 'X7','Qora',2015,75000)
salon1 + avto7
print(salon1[:])
```

Natija: \[Avto: Qora GM Malibu, Avto: Oq GM Lacetti, Avto: Silver Toyota Carolla, Avto: Qora BMW X7]

Huddi shu kabi boshqa operatorlarni ham o'zingiz istalgancha talqin qilishingiz mumkin:

| Operator     | Metod     |
| ------------ | --------- |
| Qo'shish     | `__add__` |
| Ayirish      | `__sub__` |
| Ko'paytirish | `__mul__` |
| Daraja       | `__pow__` |
| Bo'lish      | `__div__` |

## OBYEKTNI CHAQIRISH

Obyektlarni huddi funksiyalarni chaqirgandek chaqirish ham mumkin. Odatda biror funksiyaga murojat qilganda funksiya nomidan so'ng qavslar ochiladi va yopiladi. Agar funksiya argument qabul qilsa, ular qavs ichida beriladi.&#x20;

```python
>>> print(10)
10
>>> len("salom")
5
```

Biz obyektimizga ham shunday imkoniyat qo'shishimiz mumkin. Buning uchun maxsus `__call__` metodidan foydalaniladi.

### PARAMETRSIZ CHAQIRISH

Misol uchun, kelign yuqoridagi `AvtoSalon` klassiga oid obyektlar chaqirilganda salondagi avtomobillar ro'yxatini ko'rsatadigan qilaylik. Buning uchu `AvtoSalon` klassiga quyidagi metodni qo'shamiz:

```python
    def __call__(self):
        return [avto for avto in self.avtolar]
```

Mana endi obyekt chaqirib ko'ramiz:

```python
salon1()
```

Natija: `[Avto: GM Malibu. 40000$,
 Avto: GM Lacetti. 20000$,
 Avto: Toyota Carolla. 45000$]`

### PARAMETR BILAN CHAQIRISH

Yuqorida salon1 ni parametrsiz chaqrishini ko'rdik. Keling endi parametr bilan chaqirishni ham yo'lga qo'yaylik. Bunda, yuborilgan parametr yangi avto obyekti bo'lsin, va bu parametr salondagi avtolar ro'yxatiga qo'shilsin. Metodimizni quyidagicha o'zgartiramiz:

```python
    def __call__(self,*param):
        if param: # agar parametr bo'lsa
            for avto in param:
                self.add_avto(avto)
        else: # agar parametr bo'lmasa
            return [avto for avto in self.avtolar]
```

Endi bizning klassimizga ham parametr bilan, ham parametrsiz chaqirish imkoniyati qo'shildi.

```python
avto_new = Avto("Mercedes-Benz", 'E200','Silver',2015,80000)
salon1(avto_new) # Yangi avto qo'shamiz
salon1() # salondagi mashinalarni ko'ramiz
```

Natija: `[Avto: GM Malibu. 40000$, Avto: GM Lacetti. 20000$, Avto: Toyota Carolla. 45000$, Avto: Mercedes-Benz E200. 80000$]`

`__call__` metodini qanday talqin qilish ham sizning ihtiyoringizda.

## SO'NGSO'Z

Ushbu bo'limda biz maxsus metodlarning ba'zilari bilan tanishdik. Bu metodlarning qulayligi shundaki, siz ularni istalgacha talqin qilishingiz va har bir obyekt uchun mos keladigan qilib yaratishingiz mumkin. Ko'rib turganingizdek dunder metodlar obyektingizning imkoniyatlarini kengaytiradi va ularga qo'shimcha vazifalar yuklaydi.

## AMALIYOT

* Avvalga darslarda yaratilgan obyektlarga (`Shaxs`, `Talaba`) turli dunder metodlarni qo'shishni mashq qiling.&#x20;
  * Obyekt haqida ma'lumot (`__rerp__`)
  * Talabalarni bosqichi bo'yicha solishtirish (`__lt__`,`__eg__` va hokazo)
* Fan degan yangi klass yarating. Fan obyetklari tarkibida shu fanga yozilgan talabalarning ro'yxati saqlansin. Buning uchun Fanga add\_student(), `__getitem__`, `__setitem__`, `__len__` kabi metodlarni qo'shing.
* Fanga qo'shish `+` operatori yordamida talaba qo'shish metodini yozing
* Minus (`-`) operatori yordamida fandan talaba olib tashlash metodini yozing (bunda talabaning passport raqami yoki ID raqami bo'yicha topib, olib tashlash mumkin)
* Fan obyektlarini chaqiriladigan qiling (masalan, `fizika()`, yoki `fizika(talaba1)`). Bu metodlarni o'zingiz istagandek talqin qiling.

## KODLAR

### GitHub

{% embed url="<https://github.com/anvarnarz/python-darslar>" %}

### Repl.it

{% embed url="<https://repl.it/@anvarbek/darslar-32-dunder>" %}


---

# Agent Instructions: Querying This Documentation

If you need additional information that is not directly available in this page, you can query the documentation dynamically by asking a question.

Perform an HTTP GET request on the current page URL with the `ask` query parameter:

```
GET https://python.sariq.dev/oop/32-dunder-metodlar.md?ask=<question>
```

The question should be specific, self-contained, and written in natural language.
The response will contain a direct answer to the question and relevant excerpts and sources from the documentation.

Use this mechanism when the answer is not explicitly present in the current page, you need clarification or additional context, or you want to retrieve related documentation sections.
