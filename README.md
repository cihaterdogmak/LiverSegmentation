# Karaciğer Segmentasyonu Projesi: Lightweight DeepLabV3+ Kullanımı

Bu proje, tıbbi görüntülerde **karaciğer segmentasyonu** gerçekleştirmek için **DeepLabV3+ MobilNetV3 Large** modelini kullanmaktadır. Proje, eğitilmiş modeli kullanarak görüntüler üzerinde segmentasyon yapabilir ve ilgili maskeleri oluşturabilir.

## Canlı Test Ortamı
Proje, **İnönü Üniversitesi Medikal Görüntü İşleme Sistemi** üzerinde test edilebilir:
🔗 **[Test Etmek İçin Tıklayın](https://medikal.inonu.edu.tr/proje-detay/985/)**

- Görseller bu siteye yüklenerek test edilebilir.
- **Sonuçlar** sekmesinden çıktı kontrol edilebilir.
- **Önerilen Görüntü Boyutu:** Daha iyi sonuç almak için 512x512 piksel önerilir.

---

## İçerik ve Kullanım

### 🔹 Eğitim ve Test Kodu
Eğitim ve test süreçleri **`deeplabv3TrainingandTest.ipynb`** dosyasında bulunmaktadır.

- **Model**: DeepLabV3+ MobilNetV3 Large
- **Cihaz Desteği**: GPU veya CPU uyumlu
- **Veri Seti**: Karaciğer segmentasyonu için hazırlanmış özel veri seti

### 🔹 Önişleme
Önişleme adımları **`önisleme.ipynb`** dosyasında tanımlanmıştır. Bu, projeyi çalıştırmak için zorunlu değildir ancak model performansını iyileştirebilir.

📌 **Önemli Önişleme Adımları:**
- L1/L2 norm normalizasyonu
- Median ve adaptif median filtreleme
- Min-Max normalizasyonu
- Histogram eşitleme
- Gamma düzeltmesi
- Kenar tespiti (Sobel, Canny, Laplacian)

---

## 📌 Model ve Eğitim Süreci

- **Model Çıkışı**: Tek sınıflı segmentasyon maskesi
- **Kayıp Fonksiyonu**: Binary Cross Entropy (`BCEWithLogitsLoss`)
- **Optimizasyon**: Adam optimizatörü kullanıldı
- **Performans Metrikleri**: **Intersection over Union (IoU)** metriği ile değerlendirme yapıldı

### 🎯 IoU Hesaplama
Modelin başarımı, **IoU (Intersection over Union)** metriği ile ölçülmektedir:
IoU = Kesişim / (Birleşim + 1e-6)

- Yüksek IoU = Daha başarılı segmentasyon
- Model, en iyi ve en kötü eşleşmeleri görselleştirmektedir.

---

## 🖥 Site Entegrasyonu İçin Python Kodu
- MedicalinonuExecScript.py belgesini inceleyerek gerekli koda ulaşabilirsiniz


## 📂 Veri Seti (DB Klasörü)
- Veri seti, 50 farklı hastadan alınan 3 boyutlu görüntülerin rastgele kesitlerinden oluşturulmuştur.

- images/ klasörü: Ham görüntü verileri
- labels/ klasörü: Segmentasyon için kullanılan maske verileri
# 📌 Etiketler, ilgili görüntülerin karaciğer segmentasyonu ile eşleşmektedir.

## 🔍 Sonuç
- Bu proje, karaciğer segmentasyonu için hafif ama etkili bir çözüm sunmaktadır. DeepLabV3+ MobilNetV3 Large modeli ile optimize edilmiş olup, sağlık bilişimi alanında kullanılabilir bir sistem geliştirilmiştir.

## 🚀 Daha fazla bilgi ve katkı için lütfen proje dökümantasyonunu inceleyin!








