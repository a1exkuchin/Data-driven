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

### Клонируем репозиторий и создаем образ
```
$ git clone https://github.com/fimochka-sudo/GB_docker_flask_example.git
$ cd GB_docker_flask_example
$ docker build -t fimochka/gb_docker_flask_example .
```

### Запускаем контейнер

Здесь Вам нужно создать каталог локально и сохранить туда предобученную модель (<your_local_path_to_pretrained_models> нужно заменить на полный путь к этому каталогу)
```
$ docker run -d -p 8180:8180 -p 8181:8181 -v <your_local_path_to_pretrained_models>:/app/app/models fimochka/gb_docker_flask_example
```

### Переходим на localhost:8181
