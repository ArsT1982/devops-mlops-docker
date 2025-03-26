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

