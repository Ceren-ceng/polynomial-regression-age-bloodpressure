

## 🩺 Polinom Regresyon (3. Derece) — Yaş & Tansiyon Tahmini

**Dosya:** `polynomial_regression_age_bloodpressure.ipynb`

### 📋 Problem Tanımı

- **Amaç:** Bir kişinin yaşına bakarak tansiyonunu tahmin edebilen bir polinom regresyon modeli kurmak.
- **Veri Seti:**  
  - 100 kişinin rastgele belirlenen yaşı (18-80 arası, bazı yaşlar birden fazla kişide tekrar edebilir)
  - Tansiyonlar:  
    `tansiyon = 0.0001 * yaş³ - 0.01 * yaş² + 1.5 * yaş + 70 + gürültü`  
    (gürültü: ortalama 0, standart sapma 5 ile küçük farklılıklar eklendi — gerçek hayattaki ölçüm hatalarını veya kişisel farklılıkları simüle etmek için)
- **Model:** 3. derece (cubic) polinom regresyon, scikit-learn ile

---

### ⚙️ Uygulama ve Kullanım

- **Veri Ayrımı:** Eğitim (%80) ve test (%20) verileri ayrılmıştır.  
  Böylece model hem öğrendiği veride, hem de “hiç görmediği” yeni yaşlarda ne kadar doğru tahmin yapabiliyor analiz edilir.
- **Özellik Oluşturma:**  
  Yaş, yaş² ve yaş³ otomatik olarak modele eklenir (polynomial features).
- **Model Eğitimi:**  
  Model, polinomun katsayılarını ve bias’ı otomatik bulur.
- **Tahmin:**  
  Test verisinin tümünde modelin tahmini ve gerçek değerler grafik üzerinde karşılaştırılır.
- **Bireysel Tahmin:**  
  Kod içinde  
  ```python
  yeni_yas = 38 satırı ile istenen herhangi bir yaş girilebilir!
Örneğin yeni_yas = 60 yaparsan, model 60 yaşındaki biri için tahmin üretir.
Grafikte bu değer özel işaretle (yeşil yıldız) gösterilir.
Tablo Analizi:
Veri setinde aynı yaşa sahip birden fazla kişi varsa, bunlar ayrıca listelenir. Gerçek hayatta aynı yaşta insanların tansiyonlarının farklılık gösterebileceğini gözlemleyebilirsin.

📊 Sonuçlar ve Analiz
Katsayılar:
Model çıktı olarak “yaş”, “yaş²”, “yaş³” ve sabit (bias) katsayılarını gösterir. Bu katsayılar, yaşın tansiyon üzerindeki etkisinin doğrusal değil, eğrisel (nonlineer) olduğunu gösterir.

Eğitim ve Test Hataları:

Eğitim MSE (Train MSE): Model, gördüğü verilerde ne kadar hata yapıyor?

Test MSE (Test MSE): Model, hiç görmediği yaşlarda ne kadar hata yapıyor?

R² Skoru: 1’e ne kadar yakınsa model o kadar iyi!
(Eğitimde yüksek, testte düşerse overfitting olabilir.)

Grafik Analizi:

Mavi noktalar: Gerçek test verisi (yani ölçülen tansiyonlar)

Kırmızı noktalar: Modelin aynı yaşlar için tahmini

Yeşil yıldız: Senin belirlediğin yaştaki kişinin tahmin edilen tansiyonu

Model, yaş arttıkça tansiyondaki değişimi yakalamak için eğrisel bir fonksiyon öğrenir.

Ekstra Tablo:
Aynı yaşa sahip kişilerin ölçümlerine bakarak, modelin gerçek hayattaki “bireysel farklılıkları” ne kadar hesaba katabildiğini görebilirsin.
Anahtar Kelimeler:
- machine-learning
- polynomial-regression
- health-data
- sklearn
- python
- tutorial
- regression
- nonlinear
- analysis
Sorularınız için geri dönüş yapabilirsiniz. :)
