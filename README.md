## Многоклассовая классификация изображений по небольшому объёму данных: определение на фотографии птицы или БПЛА

#### Оглавление
- [Цель проекта](#цель-проекта)
- [Описание проекта](#описание-проекта)
- [Подготовка датасета](#подготовка-датасета)
- [Результаты работы](#результаты-работы)
- [Структура репозитория](#структура-репозитория)
- [Источники](#источники)
- [Авторы](#авторы)


### Цель проекта

Решение задачи в рамках учебного хакатона по классификации изображений. Сбор и подготовка датасета.
Обучение предобученной нейросети для определения птицы/БПЛА на фото.

### Описание проекта

Нейронная сеть была обучена на распознавание объектов двух классов (птица и БПЛА) с использованием моделей EfficientNetB0, EfficientNetB7 и EfficientNetV2M.
Если на фотографии птица, то значение стремится к 0, если БПЛА, то к 1. Датасет разбит на 2 части: test и train в соотношении 15%/85%. При начальном размере датасета в 600-700 фотографий для каждой категории результаты получались 0.6 для БПЛА и 0.3 для птиц соответственно, в связи с чем было принято решение увеличить размер датасета. При размере датасета в 2176(train) и 386(test) фото для БПЛА, и 3225(train) и 571(test) фото для птиц результаты получились оптимальными.

### Подготовка датасета

Датасет собирался из различных открытых источников:
Скриншоты из видео на youtube.com - [дроны](https://youtu.be/nzvISPjWJcI?t=660), [птицы](https://www.youtube.com/watch?v=zxzUW3Xw0-Y),
Yandex Картинки,
Google Картинки,
Готовый [датасет](https://lila.science/datasets/caltech-camera-traps)

После сбора данные в виде фотографий были отсортированы и собраны в [датасет Dropbox (zip)](https://www.dropbox.com/scl/fo/3wvoxavz83ym6obt2ktr1/h?dl=0&rlkey=w85abmidyfjusl91veyosay29) / [Google Drive](https://drive.google.com/drive/folders/1PjSBL6W4I8o9_NLbFEp0-ZQqAALrRjSu)

### Результаты работы

![image](https://user-images.githubusercontent.com/118006933/213861570-2bfd95b9-f0b6-4cf5-955c-da9a355d299e.png)

Как можем видеть, максимально точно сеть отработала с использованием модели EfficientNetB7, но и время обучения там получилось максимальным.

Ссылка на [Google Colab](https://colab.research.google.com/drive/1Hpl_3_qmKMLv7sdCWR6-C5Li6F_ZvCb_#scrollTo=vVuZxS7MbQNQ)

### Структура репозитория
Каталог notebook содержит решение в формате Jupyter Notebook.

### Источники

1. [Дукументация EfficientNet на pytorch.org](https://pytorch.org/vision/stable/models/efficientnet.html)
2. [Wiki: Transformer](https://en.wikipedia.org/wiki/Transformer_(machine_learning_model)), ([на русском](https://ru.wikipedia.org/wiki/%D0%A2%D1%80%D0%B0%D0%BD%D1%81%D1%84%D0%BE%D1%80%D0%BC%D0%B5%D1%80_(%D0%BC%D0%BE%D0%B4%D0%B5%D0%BB%D1%8C_%D0%BC%D0%B0%D1%88%D0%B8%D0%BD%D0%BD%D0%BE%D0%B3%D0%BE_%D0%BE%D0%B1%D1%83%D1%87%D0%B5%D0%BD%D0%B8%D1%8F)))
3. [Дукументация EfficientNet на keras.io](https://keras.io/examples/vision/image_classification_efficientnet_fine_tuning/)

### Авторы
- [Искужин Иремель](https://github.com/Lemeri02)
- [Акинин Дмитрий](https://github.com/AkininD)
- [Ахметов Вадим](https://github.com/vadim328)
- [Киселев Павел](https://github.com/indianlyc)
- [Гмырин Виктор](https://github.com/Victor-Gmyrin)
