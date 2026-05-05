# #20 QIYMAT QAYTARUVCHI FUNKSIYA

<Embed url="https://www.youtube.com/watch?v=VqEWbr1erXc" />

Avvalgi darsimizda yaratgan barcha funksiyalarimiz konsolga ma'lumot chiqarayotgan edi. Aslida, aksar holatlarda bu g'ayritabiiy. Sababi, dasturchi sifatida biz konsolga chiqqan ma'lumotdan unumli foydalana olmaymiz. Konsoldagi qiymatni o'zgaruvchiga yuklab, undan kelajakda foydalanib ham bo'lmaydi. Mana shunday holatlarda, funksiyadan unumli foydalanish uchun undan biror qiymatni qaytarish maqsadga muvofiq bo'ladi.

## FUNKSIYADAN ODDIY QIYMAT QAYTARISH

Keling `ism` va `familiya` degan parametrlarni olib, `toliq_ism` qaytaradigan sodda funksiya yasaymiz.

```python
def toliq_ism_yasa(ism, familiya):
    """Toliq isma qaytaruvchi funksiya"""
    toliq_ism = f"{ism} {familiya}"
    return toliq_ism # qiymat qaytarish uchun return operatorini ishlatamiz
```

Yuqoridagi funksiyamizga ahamiyat bersangiz, uning badanida endi `print()` funksiyasi yo'q. Buning o'rniga, funksiyamiz `return` operatori yordamida `toliq_ism` degan o'zgaruvchining **qiymatini** qaytaradi.

Endi funksiyadan to'g'ri foydalanish uchun u qaytargan qiymatni biror o'zgaruvchiga yuklashimiz kerak:

```python
talaba1 = toliq_ism_yasa('olim','hakimov')
talaba2 = toliq_ism_yasa('hakim','olimov')
```

Yuqoridagi kodlarni bajarganimizda konsolga hech narsa chiqmaydi. talaba1 va talaba2 o'zgaruvchilarining qiymatini ko'rish uchun esa print() funksiyasidan foydalanamiz.

```python
print(f"Darsga kelmagan talabalar: {talaba1} va {talaba2}")
```

Natija: `Darsga kelmagan talabalar: Olim Hakimov va Hakim Olimov`

Demak, qiymat qaytaradigan funksiyaning afzalligi shundaki, biz bu qiymatlardan keyin ham bemalol foydalanishimiz mumkin.

:::danger
Funksiya ichidagi o'zgaruvchilar **mahalliy** yoki **ichki o'zgaruvchilar** deyiladi (**local variables**). Ichki o'zgaruvchilar faqatgina funksiya ichida mavjud bo'ladi, ularga tashqaridan murojat qilib bo'lmaydi. Shuning uchun ham funksiya o'zgaruvchi emas **qiymat qaytaradi**.
:::

## IXTIYORIY ARGUMENTLAR

Avvalgi darsizmida funksiyalarga standart parametr berishni ko'rgan edik. Huddi shu usul bilan, ba'zi argumentlarni ixtiyoriy qilishimiz mumkin. Ya'ni funksiya ishlashi uchun bu agrumentarni kiritish majburiy emas, ixtiyoriy bo'ladi.

Keling avvalgi funksiyamizni o'zgartiramiz va unga yana bitta otasiningismi degan paramter qo'shamiz, lekin bu parametr ixtiyoriy bo'ladi. Buning uchun funksiya yaratishda `otasining_ismi=''` deb yozib ketamiz.

```python
def toliq_ism_yasa(ism, familiya, otasining_ismi=''):
    """Toliq isma qaytaruvchi funksiya"""
    if otasining_ismi: # otasining_ismi mavjudligini tekshiramiz
        toliq_ism = f"{ism} {otasining_ismi} {familiya}"
    else:
        toliq_ism = f"{ism} {familiya}"
    return toliq_ism.title()
```

Yuqoridagi funksiyani tahlil qiladigan bo'lsak, 3-qatorda biz otasiningismi parametri bo'sh yoki yo'qligini tekshiramiz. Pythonda `if` dan so'ng bo'sh bo'lmagan matn (string) yozsak, bu shart `True` qaytaradi. Demak, bu ixtiyoriy parametr kiritilgani yoki yo'qligiga qarab, funksiyamiz turlicha qiymat qaytaradi.

```python
talaba1 = toliq_ism_yasa('olim','hakimov') #otasining_ismi kiritilmadi
talaba2 = toliq_ism_yasa('hakim','olimov','abrorovich')
print(f"Darsga kelmagan talabalar: {talaba1} va {talaba2}")
```

Natija: `Darsga kelmagan talabalar: Olim Hakimov va Hakim Abrorovich Olimov`

## FUNKSIYADAN LUG'AT QAYTARAMIZ

Funksiyadan sodda qiymat emas, ro'yxat, lu'gat va boshqa ma'lumot turlarini ham qaytarishimiz mumkin.  Quyidagi funksiya ham mashina haqidagi ma'lumotlarni jamlab, ularni lug'at ko'rinishida qaytaradi:

```python
def avto_info(kompaniya, model, rangi, korobka, yili, narhi=None):
    avto = {'kompaniya':kompaniya,
            'model':model,
            'rang':rangi,
            'korobka':korobka,
            'yil':yili,
            'narh':narhi}
    return avto
```

E'tibor bering, `narhi` nomli parametrga `None` standart qiymatini berib ketdik. `None` Pythonda *mavjud emas* ma'nosini beradi, va `if` yordamida tekshirganda `False` mantiqiy qiymatini qaytardi.

Quyidagi kodni tahlil qilishni sizga vazifa sifatida qoldiramiz:

```python
avto1 = avto_info('GM','Malibu','Qora','Avtomat',2018)
avto2 = avto_info('GM','Gentra','Oq','Mexanika',2016,15000)
avtolar = [avto1, avto2]
print('Onlayn bozordagi mavjud avtomashinalar:')
for avto in avtolar:
    if avto['narh']:
        narh = avto['narh']
    else:
        narh = "Noma'lum"
    print(f"{avto['rang']} {avto['model']}. Narhi: {narh}")
```

![Natija](../cirth-assets/9a7e25a9-d775-43ad-8c99-22197d672a51.png)

## FUNKSIYADAN RO'YXAT QAYTARAMIZ

Biz avvalroq `range()` funksiyasi bilan tanishgan edik. Bu funksiya 2 ta son qabul qilib, shu ikki son orali'g'idagi sonlarni qaytaradi. Keling biz `oraliq()` degan yangi funksiya yaratamiz. `range()` dan farqli ravishda, funksiyamiz 2 son oralig'idagi sonlarni **ro'yxat** ko'rinishida qaytarsin.

```python
def oraliq(min,max):
    sonlar = [] # bo'sh ro'yxat
    while min<max:
        sonlar.append(min)
        min += 1
    return sonlar
```

Funksiyani tekshiramiz:

```python
print(oraliq(0,10))
print(oraliq(10,21))
```

![Natija](../cirth-assets/9c15c2cb-5f20-4f45-8502-84a9fb2f8a66.png)

Yuqoridagi funksiyaga uchinchi, `qadam` deb nomlangan ixtiyoriy parameterni qo'sha olasizmi?

```python
print(oraliq(0,21,2)) # 0 dan 21 gacha 2 qadam bilan
```

Natija: `[0, 2, 4, 6, 8, 10, 12, 14, 16, 18, 20]`

## FUNKSIYALARNI TSIKLDA ISHLATISH

Funksiyalarni takrorlash uchun tsikldan foydalanishimiz mumkin. Quyidagi misolda biz `while` yordamida avvalroq yaratgan `avto_info` funksiyamizni bir necha bor chaqiramiz va salondagi avtolar ro'yxatini shakllantiramiz. Bunda, ro'yxatning har bir elementi `avto_info` funksiyasidan qaytgan lug'at bo'ladi.

```python
print("Saytimizdagi avtolar ro'yxatini shakllantiramiz.")
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
```

Yuqoridagi funksiyani Pythonda bajarib kor'ing. Ro'yxatga bir necha qiymatlar qo'shing. Natijalarni konsolga chiroyli qilib chiqaring:

![Kutilgan natija](../cirth-assets/bd381780-2af8-4c09-9a75-c0d4613ba59c.png)

## AMALIYOT

1. Foydanaluvchidan ismi, familiyasi, tug'ilgan yili, tug'ilgan joyi, email manzili va telefon raqamini qabul qilib, lug'at ko'rinishida qaytaruvchi funksiya yozing. Lug'atda foydalanuvchu yoshi ham bo'lsin. Ba'zi argumentlarni kiritishni ixtiyoriy qiling (masalan, tel.raqam, el.manzil)
2. Yuqoridagi funksiyani `while` yordamida bir necha bor chaqiring, va mijozlar degan ro'yxatni shakllantiring. Ro'yxatdagi mijozlar haqidagi ma'lumotni konsolga chiqaring.
3. Uchta son qabul qilib, ulardan eng kattasini qaytaruvchi funksiya yozing
4. Foydalanuvchidan aylaning radiusini qabul qilib olib, uning radiusini, diametrini, perimetri va yuzini lug'at ko'rinishida qaytaruvchi funksiya yozing
5. Berilgan oraliqdagi [tub sonlar ](https://uz.wikipedia.org/wiki/Tub_sonlar_ro%CA%BByxati)ro'yxatini qaytaruvchi funksiya yozing (tub sonlar —faqat birga va o'ziga qoldiqsiz bo'linuvchi, 1 dan katta musbat sonlar)
6. Foydalanuvchidan son qabul qilib, shu son miqdoricha [Fibonachchi ketma-ketligidagi ](https://medium.com/@qudratxoja.musayev/fibonachchi-sonlari-va-u-haqida-qiziqarli-faktlar-47000a80264d)sonlar ro'yxatni qaytaruvchi funksiya yozing.  ***Ta’rif***: *Har bir hadi o’zidan oldingi ikkita hadning yig’indisiga teng bo’lgan ketma-ketlik Fibonachchi ketma-ketligi deyiladi. Bunda boshlang’ish had ko’pincha 1 deb olinadi.*  `1, 1, 2, 3, 5, 8, 13, 21, 34, 55,...`

## JAVOBLAR

<Embed url="https://github.com/anvarnarz/python-darslar" />