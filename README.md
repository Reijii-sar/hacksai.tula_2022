### https://hacks-ai.ru/championships/758260
# MedTech:
Создание модели прогнозирования заболеваемости населения (Калининградская область)

### Постановщик задачи
Медицинский информационно-аналитический центр Калининградской области

### Задача:
создать модель, которая способна прогнозировать количество пациентов по каждому виду заболевания согласно международной классификации болезней, в привязке к населенному пункту, месяцу и половозрастным характеристикам на основе многолетних данных. (Метрика - R2)

Лучшее мое решение на приватном датасете 0,618761

tula_3 - 0.947173 Михаил Притугин https://github.com/DAY1972/Time-prediction:  
Для решения задачи прогнозирования количества пациентов по каждому виду заболевания был использован комбинированный подход:
1) На первом шаге производилась подготовка данных и добавление новых признаков, на основе многолетних данных
2) На втором шаге специально переобучалась модель CatBoost, чтобы оценить важность признаков
3) Был обучен линейный классификатор, который использует самые важные признаки
4) С помощью анализа общей заболеваемости, а также используя предсказание линейной модели было получено результирущие решение.

tula_2 - 0.947378 Владислав Баланда https://github.com/VladKhv/tula_20222
Анализ по предыдущему году (2021) показал что количество заболевших в апреле, лучше всего коррелирует с количеством заболевших в марте (этого же 2021 года).  
2. В связи с п.1, было принято решение, делать расчет заболевших в апреле 2022, основываясь на данных марта 2022.  
3. Модель построена на объединении данных по полям "Пол", "МКБ код", "Адрес", "Возрастная категория" ('PATIENT_SEX', 'MKB_CODE', 'ADRES', 'AGE_CATEGORY') тестовых данных и тренировочных данных.  

