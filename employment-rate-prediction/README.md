# İstihdam Oranı Tahmini – Makine Öğrenmesi Projesi

Bu projede, bölgesel ve sektörel kırılımlara göre istihdam oranlarını analiz etmek ve **istihdam_orani** değişkenini tahmin edebilecek makine öğrenmesi modelleri geliştirmek amaçlanmıştır.

Proje kapsamında veri ön işleme, keşifsel veri analizi, farklı regresyon modellerinin eğitilmesi ve performanslarının karşılaştırılması gerçekleştirilmiştir.

---

## 📊 Veri Seti Bilgisi

Veri seti aşağıdaki değişkenleri içermektedir:

- **yil**: Yıl bilgisi  
- **kirilim_bir**: Birinci kırılım (sektörel / demografik)  
- **kirilim_iki**: İkinci kırılım  
- **istihdam_bin_kisi**: İstihdam edilen kişi sayısı (bin kişi)  
- **istihdam_orani**: İstihdam oranı (%) → **Hedef değişken**

---

## 🧹 Veri Ön İşleme

- Hedef değişken (**istihdam_orani**) içeren eksik satırlar veri setinden çıkarıldı.
- Kategorik değişkenler (**kirilim_bir**, **kirilim_iki**) Label Encoding ile sayısallaştırıldı.
- Sayısal değişkenler **StandardScaler** ile ölçeklendirildi.
- Ön işleme sonrası temiz veri seti `.csv` formatında kaydedildi.

---

## 📈 Keşifsel Veri Analizi (EDA)

Aşağıdaki görselleştirmeler oluşturuldu ve `outputs/` klasörüne kaydedildi:

- Kırılım değişkenlerinin dağılımları (bar plot)
- İstihdam oranı dağılımı (histogram)
- İstihdam oranı ile kişi sayısı arasındaki ilişki (scatter plot)
- Yıllara göre istihdam oranı dağılımı (boxplot)

---

## 🤖 Kullanılan Modeller

İstihdam oranı tahmini için aşağıdaki regresyon modelleri eğitildi ve karşılaştırıldı:

- Random Forest Regressor  
- Gradient Boosting Regressor  
- K-Nearest Neighbors (KNN)  
- Support Vector Regression (SVR)  
- Yapay Sinir Ağı (ANN – Basit)  
- Derin Yapay Sinir Ağı (Dropout ile)

---

## 📏 Model Değerlendirme

Modeller aşağıdaki metrikler kullanılarak test verisi üzerinde değerlendirildi:

- **R² Skoru**
- **MSE (Mean Squared Error)**
- **MAE (Mean Absolute Error)**
- **RMSE (Root Mean Squared Error)**

Model karşılaştırma sonuçları tablo halinde oluşturularak dosyaya kaydedildi.

---

## 🏆 En İyi Model

Model karşılaştırmaları sonucunda:

- **Gradient Boosting Regressor**
  - **R² Skoru: 0.91**
  - En düşük hata metrikleri (MSE & RMSE)

ile en iyi performansı göstermiştir ve **nihai model** olarak seçilmiştir.

Ayrıca model, **train-test ayrımı** ve **cross-validation** ile test edilerek genellenebilirliği analiz edilmiştir.

---

## 📁 Proje Klasör Yapısı

employment-rate-prediction/
│
├── data/
│ ├── raw/
│ │ └── istihdam-verileri.csv
│ └── processed/
│   └── istihdam_preprocessed.csv
│ 
├── notebooks/
│ ├── 01_data_exploration.ipynb
│ ├── 02_data_preprocessing.ipynb
│ └── 03_modeling.ipynb
│
├── outputs/
│ ├── raw/
│ │ ├── istihdam_bin_vs_oran.png
│ │ ├── istihdam_orani_distribution.png
│ │ ├── kirilim_bir_countplot.png
│ │ ├── kirilim_iki_countplot.png
│ │ └── yillara_gore_istihdam_orani.png
│ └── processed/
│   ├── model_comparison_results.csv
│   └── preal_vs_pred.png
│ 
├── README.md

---

## 🛠 Kullanılan Teknolojiler

- Python  
- Pandas, NumPy  
- Matplotlib, Seaborn  
- Scikit-learn  
- TensorFlow / Keras  

---

## 🎯 Sonuç

Bu çalışma, istihdam oranlarının makine öğrenmesi yöntemleriyle başarılı bir şekilde tahmin edilebileceğini göstermektedir. Ağaç tabanlı modellerin, özellikle Gradient Boosting yönteminin, veri seti üzerinde yüksek performans sunduğu gözlemlenmiştir.
