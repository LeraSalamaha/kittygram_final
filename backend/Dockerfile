# Используем официальный образ Python
FROM python:3.9

# Устанавливаем рабочую директорию
WORKDIR /app


RUN apt-get update && apt-get install -y \
    libpq-dev \
    && rm -rf /var/lib/apt/lists/*
# Копируем файл зависимостей
COPY requirements.txt .

# Устанавливаем зависимости
RUN pip install --upgrade pip && \
    pip install -r requirements.txt --no-cache-dir

# Копируем остальные файлы проекта
COPY . .

# Команда для запуска приложения
CMD ["gunicorn", "--bind", "0.0.0.0:8000", "kittygramfinal.ddns.net", "kittygram.valeriasalamaha.ru"]