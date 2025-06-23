# 🎯 OpenCV ile Görüntü İşleme Başlangıç Rehberi

📌 **Hazırlayan:** İbrahim Hakkı Harmankaya  
🔗 [Web Siteme Bakmak İçin Tıkla](https://www.hakkiharmankaya.com/)

---

## 📍 OpenCV Nedir?

OpenCV (Open Source Computer Vision Library), görsel verileri analiz etmek ve anlamlandırmak için kullanılan güçlü ve açık kaynaklı bir kütüphanedir. Bilgisayara "görmeyi öğretmek" amacıyla; yüz tanıma, nesne tespiti, şerit takibi, karakter okuma gibi birçok uygulama yapılabilir.

---

## ⚙️ Kurulum

```bash
pip install numpy
pip install opencv-python
```

---

## 📘 Temel Kullanım Adımları

### 1️⃣ Kütüphaneleri Dahil Etme

```python
import cv2
import numpy as np
from matplotlib import pyplot as plt
```

---

### 2️⃣ Resim Yükleme ve Gösterme

```python
resim = cv2.imread("ornek.jpg")
cv2.imshow("Goruntu", resim)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

---

### 3️⃣ Resim Yüklenip Yüklenmediğini Kontrol Etme

```python
resim = cv2.imread("ornek.jpg")
if resim is None:
    print("Goruntu yuklenemedi.")
else:
    print("Goruntu basariyla yuklendi.")
```

---

### 4️⃣ Gri Tonlamaya Dönüştürme

```python
gri = cv2.cvtColor(resim, cv2.COLOR_BGR2GRAY)
cv2.imshow("Gri Ton", gri)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

---

### 5️⃣ Siyah Beyaz Yapma

```python
gri = cv2.cvtColor(resim, cv2.COLOR_BGR2GRAY)
_, siyah_beyaz = cv2.threshold(gri, 127, 255, cv2.THRESH_BINARY)
cv2.imshow("Siyah Beyaz", siyah_beyaz)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

---

### 6️⃣ Bulanıklaştırma

```python
bulanık = cv2.GaussianBlur(resim, (15, 15), 0)
cv2.imshow("Bulanik Resim", bulanık)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

---

### 7️⃣ Fotoğraf Döndürme

```python
(h, w) = resim.shape[:2]
center = (w // 2, h // 2)
M = cv2.getRotationMatrix2D(center, 30, 1.0)
dondurulmus = cv2.warpAffine(resim, M, (w, h))
cv2.imshow("Dondurulmus", dondurulmus)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

---

### 8️⃣ Kenar Belirleme (Canny)

```python
kenar = cv2.Canny(resim, 100, 200)
plt.imshow(kenar, cmap='gray')
plt.axis('off')
plt.title("Kenar Tespiti")
plt.show()
```

---

## 🎯 Not

> Bu içerik, OpenCV ile görüntü işleme konusuna giriş yapmak isteyenler için hazırlanmıştır. Daha gelişmiş işlemler (OCR, derin öğrenme, nesne takibi vs.) için ileri düzey konulara göz atmanız önerilir.

---


