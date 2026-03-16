## Credit Risk Model Stability
**Цель проекта** - предсказать, какие клиенты с большей вероятностью не смогут выплатить свои кредиты. При этом важно, чтобы качество модели оставалось стабильным во времени.

В проекте использованы данные из соревания на Kaggle "Home Credit – Credit Risk Model Stability": https://www.kaggle.com/competitions/home-credit-credit-risk-model-stability/data.
Датасет содержит информацию о клиентах финансовой организации, включая данные о кредитной истории, финансовых характеристиках и взаимодействии с банком.

Особенностью задачи является использование специальной метрики Gini Stability, которая оценивает не только среднее качество модели, но и устойчивость её предсказаний на различных временных периодах.

## Основные этапы проекта:
### 1. [Data Research](https://github.com/e-afanaseva/credit-risk-model-stability-research/blob/main/1.%20Files%20Research.ipynb)
- анализ структуры данных
- исследование взаимосвязей между таблицами
### 2. [Exploratory Data Analysis](https://github.com/e-afanaseva/credit-risk-model-stability-research/blob/main/2.%20EDA.ipynb)
- объединение данных из нескольких источников
- первичная очистка, фильтрация и преобразование данных
- анализ распределений признаков
- исследование дисбаланса классов
- построение матрицы корреляции и удаление сильно коррелированных признаков
- оптимизация использования памяти
### 3. [Baseline Model](https://github.com/e-afanaseva/credit-risk-model-stability-research/blob/main/3.%20BaseLine.ipynb)
- построение базовых моделей классификации: LightGBM Baseline, Catboost Baseline, RandomForest Baseline
- расчёт метрик качества: Gini Stability, ROC-AUC, Precision, Recall, F1
### 4. [Hyperparameter Tuning](https://github.com/e-afanaseva/credit-risk-model-stability-research/blob/main/4.%20Tuning.ipynb)
- подбор гиперпараметров моделей: LightGBM, Random Forestб, CatBoost
### 5. [Model Stacking](https://github.com/e-afanaseva/credit-risk-model-stability-research/blob/main/5.%20Stacking.ipynb)
- построение ансамбля моделей
- использование мета-модели для объединения предсказаний
- cравнение результатов
### 6.[Feature Importance](https://github.com/e-afanaseva/credit-risk-model-stability-research/blob/main/6.%20Feature%20Importance.ipynb)
- анализ важности признаков Permutation Importance
- интерпретация результатов модели SHAP

## Результат
- Проведен разведочный анализ данных (EDA);
- Объединены данные из **более чем 30 таблиц**
- Количество признаков сокращено **с 461 до 245 без потери качества**
- Подобраны гиперпараметры для моделей **CatBoost и LightGBM**
- Построены ансамблевые модели (**Stacking**), что позволило повысить качество модели до **ROC-AUC=0.6873** (baseline:** 0.6692**)
- Проведена интерпретация модели с использованием **Permutation Importance и SHAP**
В результате разработана модель кредитного скоринга, позволяющая прогнозировать вероятность дефолта клиента.

**Tech Stack**: Python, Pandas, Polars, NumPy, Scikit-learn, seaborn, matplotlib, LightGBM, CatBoost, optuna, SHAP, scipy

