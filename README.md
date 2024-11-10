# COMPETITION-MODEL
# Crop Yield Prediction

Bu loyiha **RandomForest**, **Lasso**, **Huber**, va **LinearRegression** kabi bir nechta regressiya modellarini qo'llab, **Stacking Regressor** usulida qishloq xo'jaligi hosildorligini bashorat qilishga qaratilgan. Loyihada stacking usulidan foydalanilib, final model sifatida Random Forest regressor tanlangan.

## Foydalanilayotgan Kitobxonalar

Loyihada quyidagi Python kitobxonalari ishlatilgan:
- `pandas`
- `numpy`
- `sklearn`
- `warnings`

## Loyihada Foydalanilayotgan Algoritmlar

Ushbu loyiha quyidagi algoritmlarni ishlatadi:
1. **Random Forest Regressor** - asosiy bashorat modelida va stacking regressiyada final model sifatida foydalaniladi.
2. **Lasso Regression** - asosiy regressiya modeli.
3. **Huber Regressor** - asosiy regressiya modeli, yuqori qoldiqlarni yengillatish uchun ishlatiladi.
4. **Linear Regression** - asosiy regressiya modeli.

## Kod Tarkibi

1. **Ma'lumotlarni tayyorlash**:
    - **cols** funksiyasi qo'shimcha ustunlarni yaratib, foydali xususiyatlarni qo'shadi.
    - Ma'lumotlar yuklanib, `X` va `y` uchun mustaqil va bog'liq o'zgaruvchilar aniqlanadi.
    
2. **Model**:
    - `estimators` yordamida stacking regressorda foydalaniladigan modellar ro‘yxati yaratiladi.
    - Stacking uchun asosiy model sifatida `RandomForestRegressor` tanlangan.

3. **Cross-Validation**:
    - `cross_val_score` yordamida modelning o'rtacha **Mean Absolute Error** (MAE) hisoblanadi.
    
4. **Model Fit qilish va Bashorat qilish**:
    - Model `fit` metodi bilan `X_train` va `y_train` bo'yicha o‘qitiladi.
    - `y_pred` bashoratlar yaratilib, haqiqiy qiymatlarga eng yaqin bo'lgan qiymatlar aniqlanadi.
    - `mean_squared_error`, `mean_absolute_error`, va `r2_score` yordamida baholanadi.

5. **Test Ma'lumotlari bo'yicha Bashoratlar**:
    - Sinov to'plami uchun bashorat qilinadi va natijalar `submission_colab.csv` fayliga yoziladi.

## Natijalar

Modelni baholash natijalari quyidagicha:
- **Mean Squared Error (MSE)**
- **Mean Absolute Error (MAE)**
- **R^2 Score**

Baholash jarayoni kross-valitsiya orqali amalga oshiriladi va o'rtacha MAE qiymati hisoblanadi.

## Foydalanish

1. `train.csv`, `test.csv`, va `sample_submission.csv` fayllarini `data_train`, `data_test`, va `data_sample` sifatida yuklang.
2. Loyiha kodini ishlating va `submission_colab.csv` faylida bashoratlarni ko'rishingiz mumkin.

## Talablar

Python kitobxonalari talab qilinadi:
```bash
pip install pandas numpy scikit-learn
