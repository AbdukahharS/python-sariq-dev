# #39 PIP VA TASHQI KUTUBXONALAR

{% embed url="<https://youtu.be/59pGm0doHB0>" %}

## KIRISH

Avvalgi darsimizda Python bilan birga o'rnatluvchi, standart kutubxona va undagi ba'zi foydali modullar bilan tanishdik. Ushbu darsimizda esa tashqi kutubxona bilan tanishamiz. Bu kutubxonalar yillar davomida turli foydalanuvchilar tarafidan yaratilib, yangilanib kelinadi. Bunday kutubxonalarda boshqa dasturchilar o'zlari yaratgan turli paketlarni (package) boshqalar bilan ulashadi.

{% hint style="success" %}
Paket (package) —modullar yig'indisi.
{% endhint %}

Tashqi kutubxonalar va ular ichidagi paketlar shunchalik ko'pki, deyarli istalgan vazifa yoki xizmat uchun katta ehtimollik bilan kerakli dasturlar allaqachon bir nechtadan yaratilgan. Bugungi kunda Python uchun eng katta tashqi kutubxonalardan biri bu [PyPi.org](https://pypi.org/) sahifasi.

## PIP&#x20;

Tashqi paketlarni o'rnatish uchun Pythonda maxsus `pip` paket menejeri mavjud. `pip` odatda Python bilan birga o'rnatiladi, lekin turli sabablarga ko'ra kompyuteringizda `pip` o'rnatilmagan bo'lsa, uni quyidagi sahifadan yuklab olishnigiz mumkin: <https://pypi.org/project/pip/>

Paket menejer yordamida tashqi paketlarni o'rnatish juda oson, buning uchun Windows terminalda (cmd) (yoki  Spyder konsolida, yoki  PyCharm konsolida va hokazo)`pip install paket_nomi` komandasidan foydalanasiz.&#x20;

Paket nomi qanday yozilishini paketning rasmiy sahifasidan ko'rib olishingiz mumkin. Misol uchun, quyidagi rasmda googletrans paketinig sahifasi va pip komandasi qanday yozilishi ko'rsatilgan.

![googletrans paketi sahifasi](https://1283015017-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-MGbkqs1tROquIT6oqUs%2F-MVW5aHZhPPV7qPvjU1G%2F-MVWFLRB9W5-YpZoHH6M%2Fimage.png?alt=media\&token=87573a6a-c46c-4627-8308-042ef8baaa63)

Demak ushbu paketni o'rnatish uchun `pip install gooletrans` deb yozamiz.

![googletrans paketi o'rnatilish jarayoni](https://1283015017-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-MGbkqs1tROquIT6oqUs%2F-MVW5aHZhPPV7qPvjU1G%2F-MVWFpmQQ7lFP6qmfaJU%2Fimage.png?alt=media\&token=09403e05-533f-49d3-a4cf-2ebb1d04049d)

Biror paketni oʻchirib tashlash uchun esa `pip uninstall paket_nomi` deb yozamiz.

Ushbu darsimizning maqsadi tashqi paktelar va modullar bilan tanishish orqali, Pythonning naqadar keng qamrovli til ekanini ko'rsatish. Aslida, har bir modul haqida, ularning imkoniyatlari haqida soatlab gapirish mumkin, lekin biz vaqtni tejash maqsadida turli yo'nalishlardagi ba'zi modullar bilan tanishamiz va ularning ishlashiga sodda misollar ko'rish bilan chegaralanamiz.&#x20;

Har bir modul haqida batafsil ma'lumot olish uchun modulning sahifasiga murojat qiling.

## googletrans

`pip install googletrans`

Ushbu modul yordamida Googlening tarjimonlik xizmatiga murojat qilib, istalgan matnni turli tillarga tarjima qilishimiz mumkin. Moduldan foydalanish uchun avvalo `googletrans` modulidan `Translator` klassini import qilamiz va bu klassdan yangi obyekt yaratamiz (tarjimon). Bevosita tarjimonlik xizmatiga murojat qilish uchun tarjimon obyekti ichidagi `.translate()` metodiga murojat qilamiz va parametr sifatida tarjima qilish kerak bo'lgan matnni uzatamiz.&#x20;

```python
from googletrans import Translator
tarjimon = Translator() # Translator bu maxsus klass (tarjimon esa obyekt)
matn_uz = "Python - dunyodagi eng mashxur dasturlash tili"
tarjima = tarjimon.translate(matn_uz)
print(tarjima.text)
```

Natija: `Python is the most popular programming language in the world`

{% hint style="danger" %}
DIQQAT! Agar yuqoridagi kod xato bersa (`TKK token error`), `googletrans` modulini o'chirib tashlab, huddi shu modulning yangi versiyasini o'rnating:

`pip uninstall googletrans # modulni o'chirish`

`pip install googletrans==3.1.0a0 # yangi verisyani o'rnatish`
{% endhint %}

Agar boshqa tillarga tarjima qilish kerak bo'lsa, `.translate()` metodiga matnga qo'shimcha ravishda `dest` parametrini ham uzatamiz va bu parametrga tarjima qilinishi kerak bo'lgan tilning qisqartmasini beramiz. Tarjima uchun mavjuda tillarni quyidagi manzilfa ko'rishingiz mumkin: <https://sites.google.com/site/opti365/translate_codes>

Masalan, rus tiliga tarjima qilish ucuhn `dest='ru'` deb yozamiz.&#x20;

```python
tarjima_ru = tarjimon.translate(matn_uz, dest='ru')
print(tarjima_ru.text)
```

Natija: `Python - самый популярный язык программирования в мире`

Ingliz tilidan boshqa tillarga tarjima ham shunday:

```python
matn_en = "Tashkent is the capital of Uzbekistan"
tarjima_uz = tarjimon.translate(matn_en, dest='uz')
print(tarjima_uz.text)
```

Natija: `Toshkent - O'zbekistonning poytaxti`

Odatda, Google asl matnning tilini o'zi aniqlaydi. Lekin matn tilini ham alohida ko'rsatmoqchi bo'lsangiz, `src` parametridan foydalaning:

```python
tarjima_uz = tarjimon.translate(matn_en, src='uz', dest='uz')
```

## requests

`pip install requests`

Bu paket yordamida Pythonda veb sahifalarga murojat qilishimiz (so'rov yuborishimiz) va ulardan qaytgan ma'lumotlar ustida turli amallar bajarishimiz mumkin. Misol uchun quyida requests yordamida kun.uz sahifasini to'liqligicha toritb olamiz:

```python
import requests
from pprint import pprint

manzil= "https://kun.uz/news/main"
r = requests.get(manzil)
pprint(r.text)
```

Ko'pincha requests paketidan APIlar bilan ishlashda foydalaniladi. API bu ma'lum bir veb hizmatga so'rov yuborish orqali undan foydalanish. Misol uchun yandex tarjimonga yoki google haritalari xizmatiga requests paketi yordamida API so'rov yuborish va o'zimizga kerakli ma'lumotlarni olishimiz mumkin. API haqida kelgusida batafsil dars qilamiz. Hozir esa sodda misola bilan cheklanamiz.&#x20;

Internetda restcountries.eu sahifasi mavjud. Bu sahifa orqali dunyodagi davlatlar haqida turli maʻlumotlarni olishingiz mumkin. Sahifadan foydalanish qulay boʻlishi uchun esa, sahifa yaratuvchilari bir nechta tayyor API lar eʻlon qilishgan. Misol uchun Oʻzbekiston haqida maʻlumot olish uchun quyidagi manzilga soʻrov yuborasiz: <https://restcountries.eu/rest/v2/name/Uzbekistan>

API dan qaytgan natija JSON (lugʻat) koʻrinishda boʻladi va biz bu lugʻatdan oʻzimizga kerakli maʻlumotni sugʻurib olishimiz mumkin. Misol uchun quyidagi kodimiz APIga yuborilgan davlatning poytaxtini koʻrsatadi:

```python
country = "Uzbekistan"
url = f"https://restcountries.eu/rest/v2/name/{country}"
r = requests.get(url)
r_json = r.json()[0]
print(r_json['capital'])
```

Natija: `Tashkent`

## BeautifulSoup4

`pip install beautifulsoup4`

BeautifulSoup juda kuchli modullardan biri bo'lib, bu modul yordamida turli veb sahifalardan istalgan ma'lumotlarni yig'ishtirib (scarpping) olish mumkin. Biror kishining instagram sahifasidagi barcha rasmlar deysizmi, Facebook guruhidagi barcha postlar va izohlar deysizmi, oldi-sotdi bozoridagi e'lonlar deysizmi, marhamat, `bs4` moduli yordamida buni bemalol avtomatlashtirish mumkin.&#x20;

Odatda `bs4` moduli `requests` moduli bilan hamkorlikda ishlaydi. Keling, sodda misol kor'amiz. Avvalgi bo'limda, requests yordamida kun.uz sahifasining html kodini olgan edik. Endi esa bs4 yordamida html sahifadan oxirgi yangiliklarning mavzusini ajratib olamiz.

```python
import requests
from bs4 import BeautifulSoup

sahifa = "https://kun.uz/news/main"
r = requests.get(sahifa)


soup = BeautifulSoup(r.text, 'html.parser')
news = soup.find_all(class_="news-title") # yangiliklarning mavzusini ajratib olamiz
print(news[0].text) # eng birinchi yangilikni konsolga chiqaramiz
```

Natija: `Коронавирус: AstraZeneca гумон остида, Европада вазият оғирлашмоқда`

Bu modul haqida ham kelajakda alohida dars qilamiz.

## wordcloud va matplotlib

`pip install wordcloud`

`pip install matplotlib`

Wordcloud moduli yordamida katta matnlarda eng ko'p uchraydigan so'zlarni chiroyli qilib, so'zlar buluti chiqarish mumkin. 2020-yil yakunida, [sariqdev ](https://t.me/sariqdev)sahifasida chop etilgan mashxur blogerlarning siluetlari ham aynan shu modul yordamida qilingan.&#x20;

![wordcloud moduli mahsuli](https://1283015017-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-MGbkqs1tROquIT6oqUs%2F-MVW5aHZhPPV7qPvjU1G%2F-MVZ0KjYFs9RPPdaglja%2Fimage.png?alt=media\&token=eedc8429-758d-4961-985f-8f85f4d39a29)

`wordcloud` moduli grafiklarni chizishga mo'ljallangan `matplotlib` moduli bilan hamkorlikda ishlaydi.&#x20;

Quyida kun.uz sahifasidan olingan yangiliklar uchun so'zlar bulutini yaratishni ko'ramiz.

```python
import requests

from bs4 import BeautifulSoup
from wordcloud import WordCloud 
import matplotlib.pyplot as plt 


sahifa = "https://kun.uz/news/main"
r = requests.get(sahifa)

soup = BeautifulSoup(r.text, 'html.parser')
news = soup.find_all(class_="news-title")
matn=""
for n in news:
    matn += n.text

# kerakmas so'zlar
stopwords = ["учун","бўйича","лекин","билан","ва","бор","ҳам","хил","йил"]
# bulutni yaratamiz
wordcloud = WordCloud(width = 1000, height = 1000, 
                background_color ='white', 
                stopwords = stopwords, 
                min_font_size = 20).generate(matn) 
  
# plot the WordCloud image                        
plt.figure(figsize = (8, 8), facecolor = None) 
plt.imshow(wordcloud) 
plt.axis("off") 
plt.tight_layout(pad = 0) 
plt.show() 
```

![kun.uz da so'nggi yangiliklar](https://1283015017-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-MGbkqs1tROquIT6oqUs%2F-MVW5aHZhPPV7qPvjU1G%2F-MVZ2fE0ne2Qvq3sYYxz%2Fimage.png?alt=media\&token=b1592ce4-a480-4eee-b274-761507024acf)

## fuzzywuzzy

`pip install fuzzywuzzy`

Bu modul yordamida so'zlarni bir-biriga solishtirish yoki matnlar tarkibida kerakli so'zni topishda foydalanamiz.&#x20;

Quyidagi misolda "salom" so'zini "assalom" va "salim" so'zlari bilan naqadar o'xshashligini tekshrib ko'ramiz:

```python
from fuzzywuzzy import fuzz
print(fuzz.ratio("salom",'assalom'))
print(fuzz.ratio("salom","salim"))
```

Natija:&#x20;

```python
83
80
```

Keling endi so'zlar orasidan o'xshash so'zlarni topishni ko'ramiz. Buning uchun avvalgi darslarimizdagi [uzwords](https://github.com/anvarnarz/uzwords) modulidan foydalanamiz. Ro'yxatdan bir nechta so'zlarni ajratib olish uchun `.process.extract()` funksiyasiga murojat qilamiz.

```python
from fuzzywuzzy import process
from uzwords import words

# Matnlar orasidan 3 ta eng o'xshashlarini ajratib olish
text = "салом"
matches = process.extract(text, words, limit=3)
print(matches)
```

Natija: `[('салом', 100), ('салдом', 91), ('слалом', 91)]`

Agar yagona so'zni tanlab olish talab qilinsa `extractOne()` metodini chaqiramiz:

```python
# Matnlar orasidan eng o'xshashini topish
text = "талба"
match = process.extractOne(text,words)
print(match)
```

Natija: `('талаба', 91)`

## wxPython

`pip install wxPython`

wxPython paketi deyarli barcha operatsion tizimlarda ishlaydigan grafik interfeysli dasturlar yaratish uchun mo'ljallangan. Bu paket haqida alohida darsliklar qilish mumkin, shuning uchun biz faqatgina bitta misol bilan chegralanamiz.

```python
import wx
from googletrans import Translator

tarjimon = Translator()
class MyFrame(wx.Frame):    
    def __init__(self):
        super().__init__(parent=None, title='Oʻzbek-Ingliz Lugʻat')
        panel = wx.Panel(self)        
        my_sizer = wx.BoxSizer(wx.VERTICAL)        
        self.text_ctrl = wx.TextCtrl(panel)
        my_sizer.Add(self.text_ctrl, 0, wx.ALL | wx.EXPAND, 5)        
        
        my_btn = wx.Button(panel, label='TARJIMA')
        my_btn.Bind(wx.EVT_BUTTON, self.on_press)
        my_sizer.Add(my_btn, 0, wx.ALL | wx.CENTER, 5)        
        
        self.text_out = wx.TextCtrl(panel,style = wx.TE_READONLY)        
        my_sizer.Add(self.text_out, 0, wx.ALL | wx.EXPAND, 5)         
        panel.SetSizer(my_sizer)        
        self.Show()

    def on_press(self, event):
        value = self.text_ctrl.GetValue()
        if not value:                       
            self.text_out.SetValue("Soʻz kiritmadingiz")
        else:
            tarjima = tarjimon.translate(value, src='uz', dest='en')
            self.text_out.SetValue(tarjima.text.capitalize()) 
    

if __name__ == '__main__':
    app = wx.App()
    frame = MyFrame()
    app.MainLoop()
```

![wxPython asosida yaratilgan sodda dastur](https://1283015017-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-MGbkqs1tROquIT6oqUs%2F-MVZDERbTBK6SG-ML4NC%2F-MVZdLPtLpxlgy5jH1GB%2Fimage.png?alt=media\&token=aa22dca9-cf3e-4608-94ec-c3826e5c2be5)

## openCV

`pip install opencv-python`

openCV bu kompyuter yordamida rasm va video tasvirlar bilan ishlash uchun maxsus kutubxona. Bugungi kunda sun'iy intellekt yordamida tasvirlar bilan ishlaydigan dasturlarning deyarli barchasi openCV yordamida yaratiladi.&#x20;

Bu dastur yordamida rasm va videolardagi turli obyektlarni "ko'rish", ajratib olish mumkin. Avtomobillar nomerini aniqlash, odamlarning yuzidan tanish, obyektlarni klassifikasiya qilish kabi dasturlarning kasari aynan openCV kutubxonasi yordamida ishlaydi.

![openCV kutubxonasi yordamida obyektlarni klassifikasiya qilish](https://1283015017-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-MGbkqs1tROquIT6oqUs%2F-MVZDERbTBK6SG-ML4NC%2F-MVZfEiZbukTd3GPyULb%2Fimage.png?alt=media\&token=48059715-677d-493a-926b-6daab7bde6ef)

Bu kutubxona haqida kelajakda Sun'iy Intellektga bag'ishlangan darsliklarimizda alohida batafsil to'xtalamiz. Hozircha esa quyidagi dastur yordamida videodagi odamlarning yuzi va ko'zini ajratishga misol ko'ramiz.

```python
import cv2

cap = cv2.VideoCapture(0)
face_cascade = cv2.CascadeClassifier(cv2.data.haarcascades + 'haarcascade_frontalface_default.xml')
eye_cascade = cv2.CascadeClassifier(cv2.data.haarcascades + 'haarcascade_eye.xml')

while True:
    ret, frame = cap.read()

    gray = cv2.cvtColor(frame, cv2.COLOR_BGR2GRAY)
    faces = face_cascade.detectMultiScale(gray, 1.3, 5)
    for (x, y, w, h) in faces:
        cv2.rectangle(frame, (x, y), (x + w, y + h), (255, 0, 0), 5)
        roi_gray = gray[y:y+w, x:x+w]
        roi_color = frame[y:y+h, x:x+w]
        eyes = eye_cascade.detectMultiScale(roi_gray, 1.3, 5)
        for (ex, ey, ew, eh) in eyes:
            cv2.rectangle(roi_color, (ex, ey), (ex + ew, ey + eh), (0, 255, 0), 5)

    cv2.imshow('frame', frame)

    if cv2.waitKey(1) == ord('q'):
        break

cap.release()
cv2.destroyAllWindows()

# copyright Tim Ruscia aka techwithtim
# code from https://github.com/techwithtim/OpenCV-Tutorials
```

Natija:

![openCV yordamida videoda yuz va ko'zni aniqlash](https://1283015017-files.gitbook.io/~/files/v0/b/gitbook-legacy-files/o/assets%2F-MGbkqs1tROquIT6oqUs%2F-MVZDERbTBK6SG-ML4NC%2F-MVZgBCLAEEZY6O62z9J%2Fimage.png?alt=media\&token=ee4fb2d3-c7ce-4193-a101-9eae85e406e0)

## KODLAR

{% embed url="<https://github.com/anvarnarz/python-darslar>" %}

