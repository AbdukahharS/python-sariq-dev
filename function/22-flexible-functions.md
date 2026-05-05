# #22 MOSLASHUVCHAN FUNKSIYA (\*args, \*\*kwargs)

<Embed url="https://www.youtube.com/watch?v=uzNp5XNOZ_I" />

## MOSLASHUVCHAN FUNKSIYA

Agar funksiyangiz bir nechta argument qabul qilishi kerak bo'lsa-yu, lekin siz argumentlar sonini aniq bilmasangiz, Pythonda istalgancha qiymat qabul qiluvchi funksiya yaratish imkoniyati bor.

## `*args` USULI

Agar funksiya qabul qiladigan parametrlar soni noaniq bo'lsa, va parametrlar yagona qiymatlar ko'rinishida uzatilsa, funksiya yaratishda argumentdan avval yulduzcha qo'yiladi (`*arguments`).

Quyidagi misolni ko'raylik. `summa()` nomli funksiyamiz istalgancha sonlarni qabul qilib oladi, va ularning yi'gindisi hisoblaydi:

```python
def summa(*sonlar):
    """Kiritilgan sonlar yig'indisini hisoblaydigan funksiya"""
    yigindi = 0
    for son in sonlar:
        yigindi += son
    return yigindi
```

Bu funksiyani istalgancha parametr bilan chaqirish mumkin:

```python
print(summa(1,2))
```

Natija: `3`

```python
print(summa(1,2,3,4,5))
```

Natija: `15`

`*args` usulida, bacha uzatilgan parametrlar (bir dona bo'lsa ham) funksiya ichida [o'zgarmas ro'yxatga (tuple)](https://python.sariq.dev/ozgaruvchilar-va-malumot-turlari/08-list-tuple#tuples-ozgarmas-royxat) joylanadi. Bundan kelib chiqib, yuqoridagi funksiyamizni yanada soddalashtirib yozishimiz mumkin:

```python
def summa(*sonlar):
    """Kiritilgan sonlar yig'indisini hisoblaydigan funksiya"""
    return sum(sonlar)

print(summa(4,5,6,7))
```

Natija: `22`

Agar funksiya bir nechta argument qabul qilsa, `*args` argument doim oxirida yoziladi:

```python
def summa(x,y,*sonlar):
    """Kiritilgan sonlar yig'indisini hisoblaydigan funksiya"""
    return x+y+sum(sonlar)
```

Yuqoridagi funksiyamiz kamida 2 ta parametr qabul qiladi (`x` va `y`) va birinchi ikki argumentlar majburiy argumentlardir.

```python
print(summa(2))
```

Netija: `TypeError: summa() missing 1 required positional argument: 'y'`

## `**kwargs` USULI

Agar funksiyaga kalit so'z - qiymat ko'rinishidagi argumentlarni uzatish talab qilinsa, va bunday parametrlar soni noma'lum bo'lsa, argument oldidan ikkita yulduzcha qo'yiladi (`**kwargs`).

:::info
\*\*kwargs — keyword arguments (kalit so'zli argumentlar)
:::

```python
def avto_info(kompaniya,model,**malumotlar):
    """Avto haqidagi ma'lumotlarni lug'at ko'rinishdia qaytaruvchi funksiya"""
    malumotlar['kompaniya']=kompaniya
    malumotlar['model']=model
    return malumotlar
```

Yuqoridagi funksiyamiz kompaniya va model degan ikki qiymatni qabul qiladi, undan keyin esa funksiyaga istalgancha parametr uzatish mumkin.  Bunday funksiyaga parametrlar `kalitso'z=qiymat` ko'rinishida uzatiladi.

Funksiya ichida avval foydalanuvchi kiritgan **qo'shimcha** qiymatlardan iborat `malumotlar` deb nomlangan lug'at shakllantiriladi. Undan keyin esa majburiy parametrlarni lug'atga qo'shamiz.

```python
avto1 = avto_info("GM", "malibu", rang='qora', yil=2018)
avto2 = avto_info("Kia", "K5", rang='qizil', narh=35000)
```

```python
print(avto2)
```

Natija: `{'rang': 'qizil', 'narh': 35000, 'kompaniya': 'Kia', 'model': 'K5'}`

## **AMALIYOT**

1. Istalgancha sonlarni qabul qilib, ularning ko'paytmasini qaytaruvchi funksiya yozing
1. Talabalar haqidagi ma'lumotlarini lug'at ko'rinishida qaytaruvchi funkisya yozing. Talabaning ismi va familiyasi majburiy argument, qolgan ma'lumotlar esa ixtiyoriy ko'rinishda istalgancha berilishi mumkin bo'lsin.

## JAVOBLAR

### GitHub

<Embed url="https://github.com/anvarnarz/python-darslar" />

### Repl.it

<Embed url="https://repl.it/@anvarbek/javoblar-22-01#main.py" />

<Embed url="https://repl.it/@anvarbek/javoblar-22-02#main.py" />
