# python-flask-docker
Итоговый проект курса "Машинное обучение в бизнесе"

Стек:

ML: sklearn, pandas, numpy
API: flask
Данные: с kaggle - https://www.kaggle.com/uciml/red-wine-quality-cortez-et-al-2009

Задача: предсказать по физическим характеристикам вина (содержанию диоксида серы, рН, плотности, содержанию сахара и т.п.) качество вина по шкале от 1 до 12 (поле quality). 

Используемые признаки:


 - fixed acidity (float)
 - volatile acidity (float) 
 - citric acid (float)
 - residual sugar (float)
 - chlorides (float)
 - free sulfur dioxide (float)
 - total sulfur dioxide (float)
 - density (float)
 - pH (float)
 - sulphates (float)
 - alcohol (float)


Преобразования признаков: StandardScaler

Модель: GradientBoostingRegressor

### Клонируем репозиторий в домашнюю папку пользователя и создаем образ
```
$ git clone https://github.com/a1exkuchin/Data-driven.git
$ cd GBR_docker_flask
$ sudo docker build -t flask_docker .
```

### Запускаем контейнер


```
$ sudo docker run -d -p 8180:8180 -v ~/app/app/models flask_docker
```

### С помощью verify.ipynb проверяем работоспособность сервиса
