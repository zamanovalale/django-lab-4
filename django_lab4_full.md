Laboratoriya 4

---

## 1. Giris
Django, Python proqramlasdirma dili ucun hazirlanmis guclu ve yuksek performansli veb freymvorkdor. O, veb tetbiqlerinin suretli ve tehlukesiz sekilde inkisaf etdirilmesini temin edir. Django "bateriyalar daxil" (batteries-included) prinsipi ile gelir ve inkisaf ucun lazim olan komponentlerin ekseriyyeti artiq hazir sekilde teqdim olunur.

Django asagidaki ustunluklere malikdir:
- Tez inkisaf imkani
- Tehlukesizlik mexanizmleri
- Mohkem arxitektura
- ORM vasitesile verilenler bazasi ile rahat is
- Sablon sistemi

---

## 2. Qurasdirma

### 2.1 Python-un qurasdirilmasi
Sisteminizde Python 3 versiyasi olmalidir. Yoxlamaq ucun:
```
python --version
```
eger Python yoxdur, python.org saytindan yuklenib qurasdirilir.

### 2.2 Virtual muhitin yaradilmasi
```
python -m venv env
env\Scripts\activate
```

### 2.3 Django-nun qurasdirilmasi
```
pip install django
```

### 2.4 İlk Django layihesinin ve tetbiqin yaradilmasi
```
django-admin startproject myproject
cd myproject
python manage.py startapp main
```

---

## 3. Django'nun arxitekturasi

### 3.1 MVT
- **Model:** Verilenler bazasi ile elaqeni temin edir.
- **View:** Sorgunu qebul edib cavabi qaytarir.
- **Template:** HTML hissesidir.

### 3.2 MVC ile muqayise
Django View → MVC Controller rolunda isleyir.

---

## 4. Sade statik veb sehifenin hazirlanmasi

### 4.1 HTML sablonu
`main/templates/home.html`:
```html
<!DOCTYPE html>
<html>
<head>
    <title>Statik Sehife</title>
</head>
<body>
    <h1>Bu menim ilk Django sehifemdir</h1>
</body>
</html>
```

### 4.2 Views.py
```python
from django.shortcuts import render

def home(request):
    return render(request, "home.html")
```

### 4.3 URL-ler
`myproject/urls.py`:
```python
from django.contrib import admin
from django.urls import path
from main.views import home

urlpatterns = [
    path('admin/', admin.site.urls),
    path('', home, name='home'),
]


