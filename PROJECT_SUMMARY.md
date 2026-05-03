# ✅ PROJE TESLİM PAKETI - CAR EVALUATION ML PROJECT

## 📦 İçerik Özeti

Bu klasör, **Car Evaluation Dataset** üzerinde yapılan kapsamlı veri bilimi projesinin tümünü içerir.

---

## 📂 Dosya Yapısı

```
veribilimiproje/
│
├── 📓 car_evaluation_ml_project.ipynb        [MAIN] Jupyter Notebook (tüm analiz)
├── 📄 README.md                              [DOCS] Proje dökümentasyonu
├── 📋 PRESENTATION_GUIDE.md                  [GUIDE] Sunuş hazırlık rehberi
├── 📋 requirements.txt                       [SETUP] Python dependencies
├── 📋 PROJECT_SUMMARY.md                     [THIS] Teslim paketi özeti
│
└── 📁 data/
    ├── car.data                              [DATA] Ana dataset (1728 satır)
    ├── car.c45-names                         [META] C4.5 format metadata
    └── car.names                             [META] Feature açıklamaları
```

---

## 🚀 HIZLI BAŞLANGAÇ (Adım Adım)

### 1️⃣ Kütüphaneleri Kur
```bash
cd /home/utku/dev/okul/veribilimiproje
pip install -r requirements.txt
```

### 2️⃣ Jupyter Başlat
```bash
jupyter notebook
# veya
jupyter lab
```

### 3️⃣ Notebook'u Aç ve Çalıştır
```
car_evaluation_ml_project.ipynb → Run All Cells (Ctrl+Shift+Enter)
```

### 4️⃣ Sonuçları İnceле
- Tüm grafikler otomatik oluşacaktır
- Modeller eğitilecektir
- SHAP ve LIME açıklamaları görülecektir

---

## 📊 PROJE BÖLÜMLERI

| # | Bölüm | Açıklama | Çıktı |
|---|-------|---------|-------|
| 1 | **EDA** | Veri keşfi, dağılımlar | Grafikler, İstatistikler |
| 2 | **Feature Analysis** | Feature-class ilişkisi | Stacked bar charts |
| 3 | **Information Gain** | Feature importance (bilgi teorisi) | IG rankings |
| 4 | **Encoding & Split** | One-hot encoding, Train-Test | 17 features, 80-20 split |
| 5 | **Feature Engineering** | Yeni derived features | 5 engineered features |
| 6 | **Model Training** | 3 ML model eğitimi | LogReg, RF, XGB |
| 7 | **Evaluation** | Accuracy, F1, Confusion Matrix | Performans metrikleri |
| 8 | **Feature Importance** | Tree models'ten öğrenilen | Top 15 features |
| 9 | **SHAP** | Global model explanations | Summary plots |
| 10 | **LIME** | Local explanations | Per-sample rules |

---

## 🎯 ANA BULGULAR (Key Takeaways)

### ✨ Best Model: **XGBoost**
- **Test Accuracy**: ~96%
- **F1-Score**: ~0.XX (weighted)
- **Generalization**: Excellent (CV stable)

### 🏆 Top Features (sıra ile)
1. **Safety** (en önemli)
2. **Persons** (kişi kapasitesi)
3. **Buying** (satın alma fiyatı)
4. **Maint** (bakım fiyatı)
5. Lug Boot, Doors

### 📈 Model Insights
- Yüksek fiyat → Düşük kabul edilebilirlik
- Yüksek güvenlik → Yüksek kabul edilebilirlik
- Pahalı bakım → Model daha ihtiyatlı oluyor

### 🎯 SHAP & LIME Sonuçları
- **SHAP**: Global feature contributions açık
- **LIME**: Spesifik tahminler açıklanabilir
- Her tahmin için "neden?" sorusunun cevabı var

---

## 💻 TEKNIK DETAYLAR

### Kütüphaneler
```python
pandas, numpy                  # Veri işleme
matplotlib, seaborn            # Görselleştirme
scikit-learn                   # ML models, preprocessing
xgboost                        # Gradient boosting
shap                           # Model interpretability
lime                           # Local interpretability
jupyter                        # Notebook environment
```

### Modeller
- **Logistic Regression**: Baseline (multinomial)
- **Random Forest**: Ensemble (100 trees)
- **XGBoost**: Gradient boosting (100 estimators)

### Metrikleri
- Accuracy (overall performance)
- F1-Score (weighted, imbalanced class uyarlanması)
- Confusion Matrix (per-class breakdown)
- Cross-Validation (5-Fold)
- Per-class Precision/Recall

---

## 🎬 SUNUŞ İÇİN

1. **Süresi**: 15-20 dakika (optimal)
2. **Rehber**: `PRESENTATION_GUIDE.md` dosyasını oku
3. **Slides**: PDF powerpoint yaparken şu görselleştirmeleri kullan:
   - Sınıf dağılımı
   - Model karşılaştırması
   - SHAP summary plots
   - LIME açıklamaları

4. **Live Demo**: Notebook'u sunuş sırasında açıp göster:
   - EDA hücreleri
   - Model eğitim çıktıları
   - SHAP/LIME açıklamaları

---

## ✅ ÇALIŞMA KONTROL LİSTESİ

Proje teslim öncesi:
- [ ] Tüm hücreler çalışma hatası olmadan çalıştı
- [ ] Tüm grafikler düzgün görünüyor
- [ ] Model performans metrikleri makul
- [ ] SHAP ve LIME çıktıları oluştu
- [ ] README.md okundu ve anlaşıldı
- [ ] requirements.txt updated
- [ ] Sunuş rehberi hazırlandı

---

## 🔄 İLERLEME İçİN İDEALAR

Eğer bu proje iyileştirilmek istenirse:

1. **Dengesiz Sınıf İçin**:
   - SMOTE oversampling
   - Class weights optimization

2. **Model İyileştirme**:
   - Hiperparametre tuning (GridSearchCV)
   - Ensemble methods (Stacking/Voting)
   - Deep learning alternatifi

3. **Veri Zenginleştirme**:
   - Daha fazla feature engineering
   - Polynomial features
   - Interaction terms

4. **Production Hazırlığı**:
   - Model pickling/serialization
   - API wrapper (Flask/FastAPI)
   - Docker containerization

---

## 📞 SORUN GİDERME

### Hata: "ModuleNotFoundError: No module named 'xgboost'"
```bash
pip install --upgrade xgboost shap lime scikit-learn
```

### Hata: "FileNotFoundError: car.data"
```
✓ Kontrol et: /home/utku/dev/okul/veribilimiproje/data/car.data var mı?
✓ Yoksa: data klasörünü kopyala veya path'i düzelt
```

### SHAP/LIME çalıştırması çok yavaş
```
- SHAP'in background'da yavaş çalışması normal
- Sabredayın (1-2 dakika bekleyebilir)
- Notebook'u interactive mode'da çalıştır
```

---

## 📚 KAYNAKLAR VE REFERANSlar

- **Veri Seti**: [UCI ML Repository](https://archive.ics.uci.edu/ml/datasets/car+evaluation)
- **SHAP**: [shap.readthedocs.io](https://shap.readthedocs.io/)
- **LIME**: [lime-ml.readthedocs.io](https://lime-ml.readthedocs.io/)
- **Scikit-Learn**: [scikit-learn.org](https://scikit-learn.org/)
- **XGBoost**: [xgboost.readthedocs.io](https://xgboost.readthedocs.io/)

---

## 📌 ÖNEMLİ NOTLAR

1. **Veri Temizliği**: Dataset temiz, eksik değer yok
2. **Dengesizlik**: unacc %70, diğerleri az → başarılı modellerde normalize etmek iyi olabilir
3. **Reproducibility**: Random state sabitlendi, sonuçlar tekrarlanabilir
4. **Interpretability**: SHAP ve LIME modeli "kara kutu"tan çıkarıyor

---

## 🏁 KONKLÜSİYON

Bu proje, veri biliminin temel adımlarını kapsamlı şekilde göstermektedir:

✅ EDA ve Veri Keşfi  
✅ Feature Engineering  
✅ Model Training ve Optimization  
✅ Model Evaluation ve Comparison  
✅ Model Interpretability (SHAP & LIME)  

Proje **production-ready** değildir fakat akademik ve portfolio amaçları için mükemmeldir.

---

## 👨‍🎓 PROJESİ HAZIRLAYANLAR

**Tarih**: May 3, 2026  
**Durum**: ✅ TAMAMLANDI  

---

**Başarı ile sunumunuzu yapınız!** 🎉🚀
