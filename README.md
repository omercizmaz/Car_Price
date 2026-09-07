# Car_Price
Testing and tuning multiple machine learning algorithms (from linear models to ensembles) to find the best performing model for predicting used car prices.

# Car Price Prediction: A Machine Learning Benchmark & Optimization Project 

## 🇬🇧 English

### Project Objective
The primary goal of this project is to benchmark a wide variety of machine learning algorithms, apply rigorous hyperparameter tuning, and scientifically determine the best-performing model for predicting used car prices based on this specific dataset.

### The Methodology & Algorithm Showdown
Instead of relying on a single algorithm, this pipeline tests and compares multiple approaches:
1.  **Baseline Testing:** Evaluated the default performances of Linear Regression, Ridge, Lasso, Decision Trees, Random Forest, AdaBoost, Gradient Boosting, XGBoost, LightGBM, and KNN.
2.  **Advanced Preprocessing:** 
    *   Transformed the `Year` column into a regression-friendly `Age` feature.
    *   Handled outliers using the IQR method.
    *   Applied the **Box-Cox transformation** to the target variable (`Price`) to stabilize variance.
3.  **Hyperparameter Tuning:** Applied optimization techniques to push the algorithms to their limits. 
4.  **True Evaluation:** All final metrics (MAE, RMSE, R2) were calculated by reversing the predictions to the original price scale (`inv_boxcox`), revealing the true generalization performance of the models and exposing "optimization illusions."

### Conclusion & Final Model
While complex ensemble models like **XGBoost** showed exceptionally high $R^2$ scores on the transformed data, translating those predictions back to the original scale revealed overfitting tendencies. 

Through systematic testing and tuning, **Lasso Regression (L1 Regularization)** emerged as the optimal algorithm for this dataset. It successfully captured the main depreciation trends without memorizing specific data points, and its L1 penalty provided automatic feature selection by zeroing out the noise.

* **Final Model:** Lasso Regression
* **Test MAE:** 1583
* **Test R2** 0.836

---

## 🇹🇷 Türkçe

### Projenin Amacı
Bu projenin temel amacı; öğrenilen çok çeşitli makine öğrenmesi algoritmalarını birbiriyle kıyaslamak (benchmark), hiperparametre optimizasyonu uygulamak ve bu veri seti üzerinde araç fiyatlarını tahmin eden en iyi modeli bilimsel ve istatistiksel kanıtlarla belirlemektir.

### Metodoloji ve Algoritmaların Kıyaslanması
Sadece tek bir modele bağlı kalmak yerine, bu çalışmada farklı yaklaşımlar test edilmiş ve karşılaştırılmıştır:
1.  **Temel (Baseline) Testler:** Lineer Regresyon, Ridge, Lasso, Karar Ağaçları, Random Forest, AdaBoost, Gradient Boosting, XGBoost, LightGBM ve KNN modellerinin varsayılan performansları ölçüldü.
2.  **Gelişmiş Ön İşleme:** 
    *   `Year` (Yıl) değişkeni, regresyona daha uygun olan `Age` (Yaş) değişkenine dönüştürüldü.
    *   Aykırı değerler IQR yöntemi ile temizlendi.
    *   Bağımlı değişkenin varyansını dengelemek için **Box-Cox dönüşümü** uygulandı.
3.  **Hiperparametre Optimizasyonu:** Algoritmaların sınırlarını zorlamak ve potansiyellerini görmek için optimizasyon teknikleri kullanıldı.
4.  **Gerçekçi Değerlendirme:** Modellerin asıl performansını görmek ve "karmaşıklık/ezberleme yanılsamasını" ortadan kaldırmak için tüm nihai metrikler (MAE, RMSE, R2), `inv_boxcox` ile orijinal fiyat ölçeğine geri dönülerek hesaplandı.

### Sonuç ve Final Modeli
**XGBoost** gibi karmaşık topluluk (ensemble) modelleri dönüştürülmüş verilerde çok yüksek $R^2$ skorları verse de, orijinal fiyat birimine dönüldüğünde modelin veriyi ezberlediği (Overfitting) gözlemlendi. 

Sistematik testler ve optimizasyonlar sonucunda, bu veri seti için en uygun algoritmanın **Lasso Regresyon (L1 Regülarizasyonu)** olduğu kanıtlandı. Lasso, veriyi ezberlemek yerine ana değer kaybı trendini yakalayarak daha başarılı bir genelleme sundu ve L1 ceza katsayısı sayesinde gereksiz gürültüleri sıfırlayarak otomatik öznitelik seçimi yaptı.

* **Final Modeli:** Lasso Regresyon
* **Test Hata Payı (MAE):** 1583
* **Test R2 Skoru:** 0.836
