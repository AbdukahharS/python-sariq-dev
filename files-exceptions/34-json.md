# #34 JSON

{% embed url="<https://www.youtube.com/watch?v=e04nahLcJR8>" %}

## JSON NIMA?

JSON (**J**ava**S**cript **O**bject **N**otation) bugungi kunda ma'lumotlarni saqlash va internet orqali uzatish uchun qo'llaniladigan eng mashxur format hisoblanadi. Dastavval JavaScript tili uchun yaratilgan bu format, bugungi kunda deyarli barcha dasturlash tillari tomonidan ishlatiladi. Qolaversa, JSON formatidagi fayllarining tarkibini oddiy matn muharriri yordamida koʻrish va tahrirlash mumkin.

Aksar holatlarda dastur va server orasidagi maʻlumotlar aynan JSON koʻrinishida uzatiladi. Quyidagi rasmda Wikipedia sahifasidan olingan maʻlumot ham JSON formatida berilgan:

![JSON](https://1283015017-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-MGbkqs1tROquIT6oqUs%2F-MTGK5piVNDB4rE0t4fd%2F-MTUQjqW0iyFOjcrXIe4%2Fimage.png?alt=media\&token=c63edbe6-f836-4d82-99bb-777cb4d10aea)

Yuqoridagi misolda maʻlumotlar Pythondagi lug'atlar kabi kalit soʻz va qiymat koʻrinishida saqlangan. Lekin, JSON yordamida biz nafaqat lug'at, balki boshqa turdagi ma'lumotlarni ham saqlashimiz mumkin. Bunda Pythondagi ma'lumot turlari, quyidagi jadval asosida, JavaScript ma'lumot turlariga konvertasiya qilinadi:

| Python | JavaScript |
| ------ | ---------- |
| dict   | Object     |
| list   | Array      |
| tuple  | Array      |
| str    | String     |
| int    | Number     |
| float  | Number     |
| True   | true       |
| False  | false      |
| None   | null       |

Demak, dasturimiz davomida maʻlumotlarni JSON ko'rinishida saqlashimiz, internet orqali boshqa foydalanuvchilarga, dasturlarga yoki serverga yuborishimiz, JSON fayllarni Pythonda ochib, unga ishlov berishimiz va turli amallar bajarishimiz mumkin.

{% hint style="info" %}
JSON o'zgaruvchilar, tarkibidan qat'iy nazar matn ko'rinishida saqlanadi.
{% endhint %}

## PYTHONDAN JSONGA

JSON maʻlumotlar va fayllar bilan ishlash uchun Pythonda maxsus `json` moduli bor. Demak, dasturimiz boshida biz bu modulni yuklab olishimiz kerak boʻladi (`import json`).&#x20;

Ma'lumotlarni JSON matniga o'tkazish uchun ikki funksiyadan foydalanamiz:&#x20;

* `json.dumps(x)` — berilgan `x` o'zgaruvchini JSON matniga o'zgartiradi
* `json.dump(x,fayl)` — berilgan `x` o'zgaruvchini JSON ga o'zgartirib, ko'rsatilgan `fayl`ga saqlaydi.

### `json.dumps()`

Ma'lumotlarni JSON formatiga o'tkazish uchun `json.dumps()` funksiyasidan foydalanamiz:

```python
import json

x = 10
x_json = json.dumps(x)

ism = "anvar"
ism_json = json.dumps(ism)

sonlar = [12, 45, 23, 67]
sonlar_json = json.dumps(sonlar)
```

JSON ma'lumotlar matn ko'rinishida saqlanadi.

```python
print(type(sonlar_json))
```

Natija: `str`

Yuqoridagi aytganimizdek, ko'p holatlarda JSON ma'lumotlar lug'at ko'rinishda uzatiladi.&#x20;

```python
bemor = {
  "ism": "Alijon Valiyev",
  "yosh": 30,
  "oila": True,
  "farzandlar": ("Ahmad","Bonu"),
  "allergiya": None,
  "dorilar": [
    {"nomi": "Analgin", "miqdori": 0.5},
    {"nomi": "Panadol", "miqdori": 1.2}
  ]
}

bemor_json = json.dumps(bemor)
```

`print()` funksiyasi yordamida JSON tarkibini ko'rishimiz mumkin:

```python
print(bemor_json)
```

Natija: `{"ism": "Alijon Valiyev", "yosh": 30, "oila": true, "farzandlar": ["Ahmad", "Bonu"], "allergiya": null, "dorilar": [{"nomi": "Analgin", "miqdori": 0.5}, {"nomi": "Panadol", "miqdori": 1.2}]}`

Yuqoridagi natija o'qish uchun noqulay ko'rinishda chiqdi. Buni to'g'rilash uchun `dumps()` funksiyasiga qo'shimcha `indent=4` parametrini beramiz. Bu parametr ma'umotlarni saqlashda chapdan qancha joy tashlashni ko'rsatadi:

```python
bemor_json = json.dumps(bemor, indent=4)
print(bemor_json)
```

Natija:

```python
{
    "ism": "Alijon Valiyev",
    "yosh": 30,
    "oila": true,
    "farzandlar": [
        "Ahmad",
        "Bonu"
    ],
    "allergiya": null,
    "dorilar": [
        {
            "nomi": "Analgin",
            "miqdori": 0.5
        },
        {
            "nomi": "Panadol",
            "miqdori": 1.2
        }
    ]
}
```

Ko'rib turganingizdek, natija o'qishga qulay ko'rinishda chiqdi.

Mavzu boshida, JSON ichidagi ma'lumotlar JavaScript ma'lumot turlariga konvertasiya qilinadi dedik. Buni yuqoridagi misolda ham ko'rishimiz mumkin (`farzandlar`, `oila`, `allergiya` kalitlari qiymatini asl lug'at bilan solishtiring).&#x20;

### `json.dump()`

Ma'lumotlarni JSON formatiga o'tkazish va faylga yozish uchun `json.dump()` funksiyasini chaqriamiz. Funksiya parametri sifatida o'zgaruvchi va fayl nomlarini ko'rsatamiz. Albatta buning uchun avval faylni yozish uchun ochgan bo'lishimiz kerak:

```python
bemor = {
  "ism": "Alijon Valiyev",
  "yosh": 30,
  "oila": True,
  "farzandlar": ("Ahmad","Bonu"),
  "allergiya": None,
  "dorilar": [
    {"nomi": "Analgin", "miqdori": 0.5},
    {"nomi": "Panadol", "miqdori": 1.2}
  ]
}

with open('bemor.json','w') as f:
    json.dump(bemor,f)
```

JSON fayl tarkibini istalgan matn muharrirda ochib ko'rishimiz mumkin:

![JSON fayl tarkibi](https://1283015017-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-MGbkqs1tROquIT6oqUs%2F-MTGK5piVNDB4rE0t4fd%2F-MTVC0ye33r6EJWPPle8%2Fimage.png?alt=media\&token=77858200-babc-472d-8edc-7277e6caae58)

## &#x20;JSONDAN PYTHONGA

JSON formatidagi ma'lumotlarni Pythondagi ma'lumot turiga keltirish uchun `json.loads()` yoki `json.load()` funksiyalaridan foydalanamiz. Yuqoridagi ka'bi, `json.loads()` funksiyasi to'g'ridan-to'g'ri JSON matn bilan ishlasa, `json.load()` funksiyasi JSON fayllarni o'qish uchun ishlatiladi.

### `json.loads()`

Bu funksiya parametr sifatida JSON matn qabul qiladi va Python o'zgaruvchiga o'tkazadi.

```python
sonlar = json.loads(sonlar_json)
bemor = json.loads(bemor_json)
print(bemor)
```

Natija:

`{'ism': 'Alijon Valiyev', 'yosh': 30, 'oila': True, 'farzandlar': ['Ahmad', 'Bonu'], 'allergiya': None, 'dorilar': [{'nomi': 'Analgin', 'miqdori': 0.5}, {'nomi': 'Panadol', 'miqdori': 1.2}]}`

E'tibor qiling, `oila` va `allergiya` kalitlarining qiymati qaytadan Python ma'lumot turlariga qaytdi.

### `json.load()`

Bu funksiya JSON fayllarning tarkibini Pythonga yuklab olish uchun ishlatiladi.&#x20;

```python
filename = 'bemor.json'
with open(filename) as f:
    bemor = json.load(f)
    
print(type(bemor))
```

Natija: `<class 'dict'>`

## JSON BILAN ISHLASH

Ko'pincha internet orqali JSON fayllarni qabul qilganimizda ma'lumotlar bir necha qavatli lug'at ko'rinishida bo'ladi. JSON matnidan aynan o'zimizga kerakli ma'lumotni ajratib olish uchun lug'atni biroz tahlil qilish, uning kalitlari va qiymatlarini topish talab qilinishi mumkin. Bu ayniqsa juda uzun JSON fayllarga tegishli. Shuning uchun JSON bilan samarali ishlash uchun [lug'atlar bilan ishlashni](https://python.sariq.dev/dictionary/15-dictionary-sets) yana bir bor takrorlab oling.

Quyidagi misolda Google Maps hizmati qaytargan JSON matni lug'at ko'rinishida berilgan. Bu Toshkent shahridagi Olmazor tumanining Geografik manzili.&#x20;

```python
{
    "address_components": [
        {
            "long_name": "Almazar District",
            "short_name": "Almazar District",
            "types": [
                "political",
                "sublocality",
                "sublocality_level_1"
            ]
        },
        {
            "long_name": "Tashkent",
            "short_name": "Tashkent",
            "types": [
                "locality",
                "political"
            ]
        },
        {
            "long_name": "Tashkent Region",
            "short_name": "Tashkent Region",
            "types": [
                "administrative_area_level_1",
                "political"
            ]
        },
        {
            "long_name": "Uzbekistan",
            "short_name": "UZ",
            "types": [
                "country",
                "political"
            ]
        }
    ],
    "formatted_address": "Almazar District, Tashkent, Uzbekistan",
    "geometry": {
        "bounds": {
            "northeast": {
                "lat": 41.3954567,
                "lng": 69.269883
            },
            "southwest": {
                "lat": 41.3249733,
                "lng": 69.16497629999999
            }
        },
        "location": {
            "lat": 41.3645355,
            "lng": 69.2281531
        },
        "location_type": "APPROXIMATE",
        "viewport": {
            "northeast": {
                "lat": 41.3954567,
                "lng": 69.269883
            },
            "southwest": {
                "lat": 41.3249733,
                "lng": 69.16497629999999
            }
        }
    },
    "place_id": "ChIJ195FnkeMrjgR3nkapKKdk7A",
    "types": [
        "political",
        "sublocality",
        "sublocality_level_1"
    ]
}
```

Keling shu ma'lumotlar orasidan tumanning geografik koordinatalrini topamiz. Avvalo, lug'atga ko'z yugurtirib chiqib, bizga kerak ma'lumotlar quyidagi ko'rinishda berilganini ko'rishimiz mumkin:

```python
"location": {
            "lat": 41.3645355,
            "lng": 69.2281531
```

Bizga aynan latitude (kenglik) va longitude (uzunlik) qiymatlari kerak. Ular esa "location" kaliti ichidagi lug'atda lat va lng kalitlariga tegishli qiymatlarda joylashgan. location kalitining o'zi ham geometry kaliti ichida joylashganini ko'rishimiz mumkin.

Demak, lu'gat ichidan lat va lng qiymatlarini olish uchun quyidagi kodni yozamiz:

```python
kenglik = data['geometry']['location']['lat']
uzunlik = data['geometry']['location']['lng']
print(f"{kenglik},{uzunlik}")
```

Natija: `41.3645355,69.2281531`

Koordinatalarni Google Mapsga kiritib ko'ramiz va quyidagi natijani olamiz.

![Olmazor tumani](https://1283015017-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-MGbkqs1tROquIT6oqUs%2F-MTVIIFylrAPKvIQemxb%2F-MTVfoMHazBweHlY7Nfm%2Fimage.png?alt=media\&token=add820af-41ab-46eb-b030-ef6ca353c871)

## AMALIYOT

* Ushbu o'zgaruvchini JSON ko'rinishida saqlang va JSON matnini konsolga chiqaring: `data = {"Model" : "Malibu", "Rang" : "Qora", "Yil":2020, "Narh":40000}`
* &#x20;Ushbu JSON matnni ko'chirib oling, va talabaning ismi va familiyasini  konsolga chiqaring: `talaba_json = """{"ism":"Hasan","familiya":"Husanov","tyil":2000}"""`&#x20;
* Yuqoridagi ikki o'zgaruvchini alohida JSON fayllarga saqlang.
* Quyidagi JSON faylni yuklab oling. Faylda 3 ta talabaning ism va familiyasi saqlangan. Ularning har birini alohida qatordan `"Ism Familiya, n-kurs, Fakultet talabasi"` ko'rinishida konsolga chiqaring.

{% file src="<https://1283015017-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-MGbkqs1tROquIT6oqUs%2F-MTVgdRJ9ZPHuoEl9qq7%2F-MTW0XsEsSxHFQphbPiH%2Fstudents.json?alt=media&token=dc85518c-4e8b-40f9-aab3-2191c3d1cf8e>" %}
students.json
{% endfile %}

* Quyidagi bog'lamaga kirsangiz, Wikipediadagi Python dasturlash tili haqidagi maqolani JSON ko'rinishida ko'rishingiz mumkin. Brauzerda chiqqan ma'lumotni JSON ko'rinishida saqlang (brauzerda Ctrl+S tugmasini bosib). Faylni Pythonda oching va konsolga maqolaning sarlavhasi (title) va qisqa matnini (extract) chiqaring: <https://uz.wikipedia.org/w/api.php?format=json&action=query&prop=extracts&exintro&explaintext&redirects=1&titles=Python>

## JAVOBLAR

{% embed url="<https://github.com/anvarnarz/python-darslar>" %}


---

# Agent Instructions: Querying This Documentation

If you need additional information that is not directly available in this page, you can query the documentation dynamically by asking a question.

Perform an HTTP GET request on the current page URL with the `ask` query parameter:

```
GET https://python.sariq.dev/files-exceptions/34-json.md?ask=<question>
```

The question should be specific, self-contained, and written in natural language.
The response will contain a direct answer to the question and relevant excerpts and sources from the documentation.

Use this mechanism when the answer is not explicitly present in the current page, you need clarification or additional context, or you want to retrieve related documentation sections.
