# devops-mlops-docker
Домашняя работа к занятию “Docker и микросервисная архитектура”

## Цель
Закрепить знания по Docker, написав Dockerfile, собрав образ и запустив контейнер.

## Задание:
Необходимо сделать dockerfile для получения рабочего контейнера.

1. образ continuumio/miniconda3:latest
2. Добавляем и делаем рабочей папкой /app
3. Создаём простой sh файл с названием 1.sh, который должен выдавать надпись “Hello Netology”.
4. скопировать этот файл внутрь контейнера и выдать ему права на исполнение.
5. Запустить установку пакетов python mlflow boto3 pymysql.
6. В конце запустить на вывод файл 1.sh.
7. После чего собрать через docker build контейнер с тегом netology-ml:netology-ml

Домашнее задание выполнить в файле readme.md в github репозитории.

Результат:

---

## Dockerfile

```Dockerfile

# Использую базовый образ miniconda
FROM continuumio/miniconda3:latest

# Устанавливаю рабочую директорию
WORKDIR /app

# Копирую скрипт внутрь контейнера
COPY 1.sh .

# Делаю скрипт исполняемым
RUN chmod +x 1.sh

# Устанавливаю нужные Python-пакеты
RUN pip install mlflow boto3 pymysql

# Скрипт при запуске контейнера - выполняется
CMD ["./1.sh"]

```

## script "1.sh"

```

#!/bin/bash

echo 'Hello Netology'

```
