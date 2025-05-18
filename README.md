# Eye Disease Detection with Transfer Learning

Bu proje, **Eye Disease Detection Dataset** adlı veri kümesi üzerinde görüntü işleme teknikleri ve transfer learning kullanarak göz hastalıklarını sınıflandırmayı amaçlamaktadır. Kullanılan dört temel sınıf şunlardır: **NORMAL**, **DRUSEN**, **DME**, **CNV**.

## 🔬 Proje Hedefleri

- Görüntü işleme adımlarıyla veri kalitesini artırmak
- Özgün bir kenar tespit filtresi geliştirmek
- ResNet50 tabanlı transfer learning ile sınıflandırma yapmak
- İşlenmiş ve işlenmemiş veriler arasında karşılaştırmalı analiz sunmak

## 🧪 Görüntü İşleme Aşamaları

Her görüntüye aşağıdaki adımlar uygulanmıştır:

1. Grayscale dönüşümü & CLAHE (Kontrast artırımı)
2. Gaussian Blur
3. Thresholding (Eşikleme)
4. Bitwise AND ile maskeleme
5. **Özgün Kenar Tespit Filtresi** (`Kabaoğlu Filtresi`)
6. Morfolojik Closing işlemi

Her kategori için işlenmiş görseller farklı klasörlerde tutulmuş ve eğitim/validasyon seti olarak ayrılmıştır.

## ⚙️ Filtre Tanımı

Geliştirilen özel filtre, merkezdeki '4' değeri ve çevresindeki '-1' değerleri ile dikey kenarları vurgulamayı hedefler. Bu sayede retina üzerindeki dikey damar yapıları daha belirgin hale getirilmiştir.

## 📊 Transfer Learning ile Eğitim

- Model: **ResNet50**
- Eğitim ve validasyon: hem orijinal hem işlenmiş veri ile yapılmıştır.
- Eğitim süreci boyunca doğruluk ve kayıp değerleri takip edilmiştir.

## 📈 Performans Karşılaştırması

| Ölçüt                  | Orijinal Veri | İşlenmiş Veri |
|------------------------|---------------|----------------|
| Doğruluk (Accuracy)     | 0.34          | 0.39           |
| Duyarlılık (Recall)     | 0.34          | 0.39           |
| Özgüllük (Specificity)  | 0.779         | 0.798          |
| Kesinlik (Precision)    | 0.32          | 0.47           |
| F1-Score                | 0.30          | 0.36           |

> 🔍 İşlenmiş veriler ile model başarımında artış gözlemlenmiştir.

## 📌 Kullanılan Teknolojiler

- Python
- OpenCV
- TensorFlow / Keras
- Matplotlib, Seaborn

---

## ✍️ Geliştirici

**İrem Kabaoğlu**  
`SAÜ - Bilişim Sistemleri Mühendisliği`  
`ISE456 - Bilgisayar Görmesine Giriş`

