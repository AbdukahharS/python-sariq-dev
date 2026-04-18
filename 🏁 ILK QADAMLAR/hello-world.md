# #02 HELLO WORLD!

{% embed url="<https://youtu.be/dguiNk8eHPY>" %}

{% hint style="info" %}
Mavzuning aksar qismi video darsimizda yoritilgan bo'lsada, quyidagi matnlarga ham ko'z yugurtirib chiqish foydadan xoli bo'lmaydi.
{% endhint %}

## SPYDER IDE BILAN TANISHAMIZ

Spyder muhiti uch qismdan iborat:

1. **Matn muharriri** —dasturlar yozish uchun.
2. **Konsol** —qisqa kodlarni bajarib, tekshirib ko'rish uchun.
3. **Qo'shimcha ma'lumotlar** oynasi. Bu yerda quyidagi ma'lumotlarni ko'rish mumkin:
   1. Turli funktsiyalar haqida yordam
   2. Dasturdagi o'zgaruvchilar ro'yhati
   3. Grafiklar
   4. Fayllar

![Spyder IDE](https://1283015017-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-MGbkqs1tROquIT6oqUs%2F-MLN7dGUlu7i5DWA0qQh%2F-MLN8tAjkGkzepC07BST%2Fimage.png?alt=media\&token=f2f96f8f-3c3a-467e-8314-7bbde0e70875)

Konsolda qisqa kodlarni bajarib, natijasini ko'rish mumkin. Misol uchun oddiy arifmetik amallarni bajarib ko'raylik:

![Konsolda qisqa buyruqlarni bajarib ko'rish mumkin](https://1283015017-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-MGbkqs1tROquIT6oqUs%2F-MLN7dGUlu7i5DWA0qQh%2F-MLN9wD_L2n5kcTn7Amu%2Fimage.png?alt=media\&token=27fc9946-8772-4303-b0cb-2547e41d7639)

## BIRINCHI DASTURIMIZ —"Hello World!"

Keling an'anaga ko'ra barcha dasturchilar birinchi yozadigan dastur, "Hello World!" dasturini yozamiz.&#x20;

Buning uchun Spyder IDE yuqorisidagi menuda **File --> New File** bo'limini tanlaymiz (yoki klaviaturada Ctrl+N tugmalarini bosamiz). Math muhrarrirda yangi, **untitled0.py** fayli yaratildi.

Faylga ma'nili nom beramiz, buning uchun **File --> Save as..** menusini tanlaymiz (yoki Ctrl+Shift+S) va yangi ochilgan oynada faylga ma'nili nom beramiz.

{% hint style="danger" %}
Faylni nomlashda quyidagi qoidalarga amal qiling:&#x20;

* Fayl nomi *qisqa, kichkina  lotin harflari bilan* va eng muhimi *bo'shliq (пробел) qo'ymasdan* yozilgan bo'lishi kerak
* Fayl nomi **.py** bilan tugashi kerak (misol uchun `faylnomi.py`)
* Faylga ikki so'zdan iborat nom qo'ymoqchi bo'lsangiz so'zlar orasini tire (-) yoki pastki chiziq (\_) bilan ajrating. Misol uchun: `hello-world.py` yoki `hello_world.py`
* Fayl nomini sonlar bilan boshlamang
  {% endhint %}

Yuqoridagi qoidalarga amal qilgan holda faylga `hello.py` deb nom beramiz (siz istlagnahca nomalshingiz mumkin) va **Save** tugmasini bosamiz.

![Faylni nomlaymiz](https://1283015017-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-MGbkqs1tROquIT6oqUs%2F-MLN7dGUlu7i5DWA0qQh%2F-MLNDDHnbGos-bUEqPGC%2Fimage.png?alt=media\&token=6f5f309f-d150-42d3-8058-c4d79b4c53ba)

Matn muharririda quyidagi kodni yozamiz:

```python
print("Hello World!")
```

**print()** bu Pythondagi mahsus funktsiya bo'lib, () ichida berilgan matn yoki ifodalarni ekranga (konsolga) chiqarish vazifasini bajaradi.&#x20;

{% hint style="info" %}
Dars davomida berilgan kodlarni albatta o'zingiz ham bajaring. **Bu juda muhim!**
{% endhint %}

Kodimizni bajarish uchun **Run** (**►**) tugmasini (yoki F5) bosamiz (yangi ochilgan oynada ham **Run** tugmasini bosamiz) va konsolda natijani ko'ramiz:

![Birinchi dasturimiz va uning natijasi](https://1283015017-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-MGbkqs1tROquIT6oqUs%2F-MLN7dGUlu7i5DWA0qQh%2F-MLNFDLHkkI8Bh_8jfxw%2Fimage.png?alt=media\&token=d5ec2e8f-9a4c-4c40-aa9f-49643f33de69)

Konsolda `Hello World!` yozuvini ko'rgan bo'lsangiz, **TABRIKLAYMIZ!** Siz Pythonda birinchi dasturingizni yozdingiz.

![](https://1283015017-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-MGbkqs1tROquIT6oqUs%2F-MLNGs84zKYqFW-aUD4M%2F-MLQ4UF-16vD1m0atzQ1%2Fbrent.gif?alt=media\&token=bf8902cc-bf6d-4dde-93d2-5cf6826f11d2)

## AMALIYOT

Spyder konsolida va matn muharririda quyidagi kodlarni yozib, bajarib ko'ring. Siz kutgan natijalar chiqdimi?

```python
print('Assalom alaykum')
```

```python
print(Hayrli tong!)
```

```python
print(2+4*2)
```

```python
print(19/5)
```

```python
print(2**4)
```
