# 🚗 Araç Değerlendirme - Kapsamlı Veri Bilimi Projesi

**Proje Adı**: Car Evaluation Dataset - Comprehensive ML Analysis with SHAP & LIME

**Amaç**: Car Evaluation dataseti üzerinde EDA, Feature Engineering, Model Training, Hyperparameter Tuning ve Model Interpretability (SHAP/LIME) analizi yapılması.

---

## 📊 Veri Seti Hakkında

- **Kaynak**: UCI Machine Learning Repository
- **Toplam Örnek**: 1728
- **Features**: 6 (tümü kategorik)
  - `buying`: Satın alma fiyatı (vhigh, high, med, low)
  - `maint`: Bakım fiyatı (vhigh, high, med, low)
  - `doors`: Kapı sayısı (2, 3, 4, 5more)
  - `persons`: Kişi kapasitesi (2, 4, more)
  - `lug_boot`: Bagaj hacmi (small, med, big)
  - `safety`: Güvenlik tahmini (low, med, high)
- **Target**: Car acceptability (unacc, acc, good, v-good)

---

## 🚀 Hızlı Başlangıç

### 1. Kurulum

```bash
# Proje klasörüne git
cd /home/utku/dev/okul/veribilimiproje

# Sanal ortam oluştur (optional ama önerilen)
python -m venv venv
source venv/bin/activate  # Linux/Mac
# veya
venv\Scripts\activate  # Windows

# Gerekli kütüphaneleri kur
pip install -r requirements.txt
```

### 2. Jupyter Notebook'u Çalıştır

```bash
# Jupyter Lab başlat
jupyter lab

# veya Jupyter Notebook
jupyter notebook
```

Ardından `car_evaluation_ml_project.ipynb` dosyasını açın.

---

## 📖 Proje Yapısı ve İçeriği

### Bölüm 1: Veri Yükleme ve EDA (📊)
- Veriyi pandas'a yükle
- Temel istatistikler ve şekil
- Eksik değer kontrolü
- Sınıf dağılımı analizi

### Bölüm 2: Feature Analizi (🔍)
- Her feature'ın kategorik değerleri
- Feature-Class ilişki görselleştirmesi

### Bölüm 3: Information Gain Hesaplama (⚡)
- Mutual Information ile feature importance
- Her feature'ın sınıflandırmaya katkısı
- Matplotlib bar chart görselleştirmesi

### Bölüm 4: Kategorik Encoding (🔧)
- One-Hot Encoding uygulaması
- Train-Test Split (80-20, stratified)
- Data preprocessing pipeline

### Bölüm 5: Feature Engineering (🛠️)
- Ordinal Encoding (price levels)
- Yeni engineered features:
  - `total_price` = buying + maint
  - `lugboot_per_person` = lug_boot / persons
  - `comfort_score` = lug_boot + persons
  - `quality_score` = safety + comfort_score
  - `value_for_money` = quality_score / (total_price + 1)

### Bölüm 6: Model Eğitimi (🤖)
- **Logistic Regression** (baseline)
- **Random Forest** (tree-based)
- **XGBoost** (boosting)
- Cross-validation (5-Fold)
- Confusion Matrix ve classification reports

### Bölüm 7: Model Değerlendirmesi (📈)
- Confusion matrix heatmaps
- Accuracy ve F1-Score karşılaştırması
- Model Performance Overview

### Bölüm 8: SHAP Interpretability (🎯)
- TreeExplainer (XGBoost)
- Feature importance (global perspective)
- Beeswarm plot (feature value → impact)
- Per-sample SHAP value analysis

### Bölüm 9: LIME Interpretability (💡)
- Local explanations
- Örnek tahminler için rule-based explanations
- Model-agnostic interpretability
- İnsan okunur kurallar

### Bölüm 10: Proje Özeti (📋)
- Ana bulgular
- Insights ve öneriler
- Sonuçlar ve çıkarımlar

---

## 🎯 Başlıca Bulgular

### 1. En Önemli Features
- **Safety** (en yüksek Information Gain)
- **Persons** (kişi kapasitesi)
- **Buying** (satın alma fiyatı)
- **Maint** (bakım fiyatı)

### 2. Model Performansı
- **XGBoost**: En yüksek accuracy (~%96)
- **Random Forest**: Eşit performans, daha interpret edilebilir
- **Logistic Regression**: Baseline (~%90 accuracy)

### 3. Feature Importance (Model Öğrenilmiş)
- Encoded features içinde `safety` variants en önemli
- `buying` ve `maint` fiyat features güçlü predictorlar
- Engineering yapılan features de başarılı

### 4. Interpretability Insights
- **SHAP**: Global feature importance ve individual SHAP values
- **LIME**: Spesifik tahminleri açıklayan yerel kurallar
- Her tahmin için "neden?" sorusunun cevabı

---

## 📁 Dosya Yapısı

```
veribilimiproje/
├── car_evaluation_ml_project.ipynb    # Ana Jupyter Notebook
├── requirements.txt                   # Python dependencies
├── README.md                          # Bu dosya
└── data/
    ├── car.data                       # Ana veri seti (1728 satır)
    ├── car.c45-names                  # C4.5 format metadata
    └── car.names                      # Feature açıklamaları
```

---

## 🔧 Teknik Detaylar

### Kütüphaneler
- **pandas, numpy**: Veri işleme
- **matplotlib, seaborn**: Görselleştirme
- **scikit-learn**: ML models ve preprocessing
- **xgboost**: Gradient boosting
- **shap**: SHapley Additive exPlanations
- **lime**: Local interpretable explanations
- **jupyter**: Interactive notebook environment

### Modeller
- Logistic Regression (multinomial, max_iter=200)
- Random Forest (100 trees)
- XGBoost (100 estimators)

### Metrikler
- Accuracy
- F1-Score (weighted)
- Confusion Matrix
- Cross-Validation (5-Fold)
- Per-class Precision, Recall

---

## 💡 Öneriler ve İlerlemeler

1. **Dengesiz Sınıflar**: Class weights veya SMOTE uygulanabilir
2. **Hiperparametre Tuning**: GridSearchCV ile optimize edilebilir
3. **Ensemble Methods**: Stacking/Voting denenebilir
4. **Deep Learning**: Neural networks alternatif olabilir
5. **Feature Selection**: Recursive elimination denenebilir

---

## 🎓 Proje Sunumu İçin Tips

1. **EDA Bulguları**: Sınıf dengesizliğini vurgula
2. **Information Gain**: Hangi features neden önemli
3. **Model Performance**: Karşılaştırma grafiği kullan
4. **SHAP**: Global interpretability göster
5. **LIME**: Birkaç örnek üzerinde açıklama yap
6. **Conclusion**: Business value ve actionable insights

---

## 📝 Notlar

- Notebook'ı çalıştırmadan önce `data/car.data` dosyasının varlığını kontrol et
- Plotlar interactive değil (static matplotlib), PDF olarak export edilebilir
- SHAP ve LIME çalıştırması biraz zaman alabilir (patience!)

---

## 👨‍💻 Geliştirici

Bu proje, Car Evaluation Dataset üzerinde kapsamlı veri bilimi analizi yapmak amacıyla oluşturulmuştur.

---

## 📚 Kaynaklar

- [UCI ML Repository - Car Evaluation](https://archive.ics.uci.edu/ml/datasets/car+evaluation)
- [SHAP Documentation](https://shap.readthedocs.io/)
- [LIME Documentation](https://lime-ml.readthedocs.io/)
- [Scikit-Learn](https://scikit-learn.org/)
- [XGBoost](https://xgboost.readthedocs.io/)

---

**Last Updated**: May 3, 2026

**Status**: ✅ Proje Tamamlandı
# car-evaluation
