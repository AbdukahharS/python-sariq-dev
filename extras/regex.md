# RegEx

`RegEx` —ANDOZA ASOSIDA MATN QIDIRISH

Pythondagi juda foydali modullardan biri bu **`re`** moduli. Bu modul yordamida biz biror matn berilgan andozaga tushish, tushmalsigini tekshrib ko'rishimiz mumkin. Yoki berilgan andoza asosida matnlar orasidan kerakli matnlarni ajratib olish mumkin.

Keling boshlanishiga sodda misol ko'ramiz. Quyida biz 3 ta so'z va so'zlarni tekshirish uchun andoza yaratdik. Quyidagi andozamiz a harfidan boshlanuvchi (`^т`), s harfiga tugovchi (р`$`), 5 harfdan iborat so'zlarni qidiradi (`^т...р$`).&#x20;

{% hint style="success" %}
Avvaliga andozalarni tushunish biroz qiyin bo'lishi mumkin, lekin vaqt o'tishi bilan andoza qanday ishlashini tushunib olasiz deb umid qilamiz.
{% endhint %}

So'zlarni andozaga solishtirish uchun `re.match()` funksiyasidan foydalanamiz. Agar tekshirgan so'zimiz andozaga mosh tushsa, `re.match()` metodi so'zni o'zini qaytaradi, aks holda `None` qiymatini qaytaradi.

```python
import re

word1 = "темир"
word2 = "томир"
word3 = "тулпор"

andoza = "^т...р"

print(re.match(andoza, word1))
print(re.match(andoza, word2))
print(re.match(andoza, word3))
```

Natija:

```python
<re.Match object; span=(0, 5), match='темир'>
<re.Match object; span=(0, 5), match='томир'>
None
```

Natijadan ko'rishimiz mumkin, `word1` va `word2` o'zgaruvchilari anfozaga tushdi, `word3` esa tushmadi.

Keling endi, so'z to'pish o'yinida ishlatilgan soz'lar ro'yxatidan foydalanamiz, va ro'yxatdan biz bergan andozaga tushuvchi so'zlarni ajratib olamiz.

```python
from uzwords import words
andoza = "^т...р$"

matches = []
for word in words:
    if re.match(andoza,word):
        matches.append(word)
print(matches)
```

Natija:&#x20;

```aspnet
['табар', 'табор', 'тавир', 'тайёр', 'татар', 'татир', 'тахир', 'тақир', 'театр', 'тембр', 'темир', 'темур', 'тенор', 'тикер', 'тихир', 'товар', 'товор', 'тожир', 'томир', 'тонер', 'тоҳир', 'триер', 'тумор', 'тўпар', 'тўпир']
```

### MetaBelgilar

MetaBelgilar (MetaCharacters) andozadagi maxsus belgilar. MetaBelgilarga quyidagilar kiradi: `[] . ^ $ * + ? {} () \ |`

Bu belgilar Python tomonidan quyidagicha talqin qilinadi:

#### **`[]` - Siz qidirayotgan belgilar (harflar, sonlar) to'plami.**

Quyidagi andoza barcha м,қ,ў harflaridan biri uchraydigan soʻzlarni topadi (bu judayam koʻp).

```python
andoza = '[мқў]'
```

Andozada har bir harfni kiritib o'tirmasdan oraliq ham berish mumkin. Misol uchun, quyidagi andoza `0` dan `9` gacha sonlar va `а` dan `г` gacha boʻlgan harflardan biri cuhraydigan soʻzlarni qidiradi.

```python
andoza='[0-9а-г]'
```

Toʻrtburchak qavs ichida `^` belgisini qoʻysak, shu harflar UCHRAMAYDIGAN soʻzlarni qidirishimiz mumkin:

```python
andoza = '[^мқў]'
```

#### ^ - Matn boshini tekshirish

Yuqoridagi koʻrganimiz kabi, ^ belgisi yordamida matn qaysi belgi (belgilar) bilan boshlanishini koʻrsatishimiz mumkin:

```python
# авв ҳарфларидан бошланган сўзларни топамиз
andoza = '^авв'
matches = []
[matches.append(word) for word in words if re.match(andoza, word)]
print(matches)
```

Natija:

```aspnet
['аввал', 'авваламбор', 'аввалан', 'аввалбоши', 'аввалги', 'аввалгидай', 'аввалгича', 'аввали', 'аввалига', 'аввало']
```

#### Nuqta

Bitta nuqta - bitta belgini anglatadi. Masalan bizga авв harflaridan boshlanadigan va kamida6 harfdan iborat so'zlarni topish talab qilinsa quyidagi andozani yozamiz:

```python
andoza = '^авв...'
```

#### $ - Matn oxirini tekshirish

Matn qaysi belgilar bilan tugashini ko'rsatuvchi MetaBelgi.

```python
# 6 harfdan iborat, лоқ bilan tugaydigan matn uchun andoza
andoza = '...лоқ$'
```

