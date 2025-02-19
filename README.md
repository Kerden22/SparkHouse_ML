
# 🏡 California Housing Price Prediction - PySpark ML Projesi

Bu proje, **California konut fiyatlarını tahmin etmek** amacıyla **Apache Spark ML** kütüphanesi kullanılarak gerçekleştirilmiştir. Projede **veri analizi, veri ön işleme, makine öğrenmesi modellerinin eğitilmesi ve görselleştirme** gibi aşamalar uygulanmıştır.

## 🚀 Proje İçeriği

- **Veri Analizi ve Temizleme**
  - Eksik değer analizi ve doldurma
  - Kategorik değişkenlerin dönüştürülmesi
  - Veri özetleme ve istatistiksel analizler

- **Makine Öğrenmesi Modelleme**
  - **Linear Regression (LR)** modeli ile temel doğrusal tahminleme
  - **Gradient Boosted Trees (GBTRegressor)** ile gelişmiş modelleme
  - Model performans karşılaştırmaları (**RMSE, R², MAE** metrikleri ile)

- **Veri Görselleştirme**
  - **Scatter Plot:** Gerçek ve tahmin edilen değerlerin karşılaştırılması
  - **Histogram:** Hata dağılımının incelenmesi
  - **Heatmap:** Özellikler arasındaki korelasyonun incelenmesi
  - **Boxplot:** Kategorik değişkenlerin konut fiyatlarına etkisinin analizi
  - **Coğrafi Haritalama:** Ev fiyatlarının harita üzerindeki dağılımı
  - **Özellik Önemi Grafiği:** Modelin hangi özelliklere daha çok önem verdiği

## 📂 Kullanılan Teknolojiler

- **Apache Spark ML** - Büyük veri işleme ve modelleme
- **PySpark** - Veri işleme ve makine öğrenmesi
- **Pandas & NumPy** - Veri analizi ve manipülasyon
- **Matplotlib & Seaborn** - Görselleştirme
- **Jupyter Notebook** - Geliştirme ortamı

---

## 📊 Veri Seti

Kullanılan veri seti: [California Housing Prices](https://www.kaggle.com/datasets/camnugent/california-housing-prices)

### **Özellikler:**
- **longitude, latitude** → Konum bilgisi
- **housing_median_age** → Bina yaşı
- **total_rooms, total_bedrooms** → Odalar ve yatak odaları sayısı
- **population, households** → Bölgedeki nüfus ve hane sayısı
- **median_income** → Bölgedeki ortalama gelir
- **ocean_proximity** → Okyanusa yakınlık (kategorik)
- **median_house_value** → Tahmin edilmesi gereken **hedef değişken** 🎯

---

## 🏗️ Veri İşleme Adımları

### 1️⃣ **Veri Yükleme ve Temizleme**
- Veride eksik değerler tespit edildi (`total_bedrooms` eksik değerleri ortalama ile dolduruldu).
- **Kategorik değişkenler** `StringIndexer` ve `OneHotEncoder` ile sayısallaştırıldı.
- **Tüm özellikler** `VectorAssembler` ile tek bir `features` vektörüne dönüştürüldü.

### 2️⃣ **Model Eğitimi**
**📌 Modeller:**
- **Linear Regression (LR)**
- **Gradient Boosted Trees (GBTRegressor)**

**📌 Performans Metrikleri:**
- **RMSE (Root Mean Squared Error)** - Ortalama tahmin hatası
- **R² (Determinasyon Katsayısı)** - Modelin açıklayıcılığı
- **MAE (Mean Absolute Error)** - Ortalama mutlak hata

### 3️⃣ **Veri Görselleştirme**
📌 **Grafikler:**
- `scatter plot` - Gerçek vs Tahmin edilen değerler
- `histogram` - Hata (residual) dağılımı
- `heatmap` - Özellik korelasyonu
- `boxplot` - Kategorik değişken etkisi
- `coğrafi harita` - Ev fiyatlarının lokasyon bazında dağılımı
- `özellik önemleri grafiği` - Modelin hangi değişkenlere önem verdiği

---

## 🎯 Sonuçlar ve Karşılaştırmalar

| Model | Eğitim RMSE | Test RMSE | Eğitim R² | Test R² | Test MAE |
|--------|------------|----------|----------|---------|---------|
| **Linear Regression** | 68,512 | 69,460 | 0.64 | 0.64 |   ----- |
| **GBTRegressor** | 46,765 | 51,786 | 0.83 | 0.80 | 35,787 |

**💡 GBTRegressor, Linear Regression modeline göre daha düşük hata ve daha yüksek R² değerine sahip olduğu için daha başarılı bir sonuç vermiştir.**

---

## ⚡ Geliştirme Önerileri

✔ **Hiperparametre optimizasyonu yapılabilir.**  
🔹 **Grid Search (ParamGridBuilder)** ile **GBT modelinin `maxDepth, maxIter` gibi parametreleri optimize edilebilir.**  



✔ **Daha fazla model denenebilir.**  
🔹 **XGBoost veya LightGBM gibi gelişmiş algoritmalarla kıyaslama yapılabilir.**  



✔ **Outlier (Aykırı Değer) Analizi Eklenebilir.**  
🔹 **Boxplot ile uç değerler temizlenerek modelin doğruluğu artırılabilir.**  



✔ **Deep Learning Alternatifleri Kullanılabilir.**  
🔹 **TensorFlow/Keras ile bir sinir ağı modeli eğiterek doğruluk artırılabilir.**  



---
### Mahmut Kerem Erden - k.erden03@gmail.com
