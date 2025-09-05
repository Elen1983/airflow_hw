Что нужно сделать
Скачать архив с проектом airflow_hw, внутри него:
шаблон DAG’а (dags/hw_dag.py),
готовый код ML-модели (modules/pipeline.py),
шаблон скрипта для прогноза моделью (modules/predict.py),
данные для обучения и тестирования (data/train, data/test),
пустые папки под сохранение ML-модели и предсказаний.

Запустить пайплайн с моделью локально и в Airflow, это обучит и сохранит объект с пайплайном лучшей модели в pickle формате:
локально: python3 modules/pipeline.py (из терминала Pycharm).
в Airflow: скопировать файл hw_dag.py в папку $AIRFLOW_HOME/dags.

После этого в интерфейсе отобразится новый DAG:
Написать код в файле modules/predict.py, который при вызове функции predict():
загружает обученную модель,
делает предсказания для всех объектов в папке data/test,
объединяет предсказания в один Dataframe и сохраняет их в csv-формате в папку data/predictions.

Проверить корректность кода, запустив его локально: python3modules/predict.py (из терминала Pycharm)
Встроить прогноз моделью в пайплайн, в котором будет 2 шага:
pipeline — здесь выполняется функция pipeline,
predict — здесь делается предикт для всех объектов и сохраняется в папку data/predictions.
Запустить пайплайн в интерфейсе Airflow и получить предикты модели.
 
В этом коде используются следующие библиотеки и инструменты:

1. Системные библиотеки и логирование:

•  logging
•  os
•  datetime
•  dill

2. Работа с данными:

•  pandas

3. Машинное обучение (scikit-learn):

•  sklearn.compose
•  sklearn.ensemble
•  sklearn.impute
•  sklearn.linear\_model
•  sklearn.model\_selection
•  sklearn.pipeline
•  sklearn.preprocessing
•  sklearn.svm
