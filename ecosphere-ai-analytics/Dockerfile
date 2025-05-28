FROM python:3.9

WORKDIR /app

# Установка системных зависимостей
RUN apt-get update && apt-get install -y \
    postgresql-client \
    && rm -rf /var/lib/apt/lists/*

# Копирование файлов проекта
COPY requirements.txt .
COPY green_platform/ ./green_platform/
COPY manage.py .

# Установка зависимостей Python
RUN pip install --no-cache-dir -r requirements.txt

# Запуск миграций и сервера
CMD ["sh", "-c", "python manage.py migrate && python manage.py runserver 0.0.0.0:8000"]