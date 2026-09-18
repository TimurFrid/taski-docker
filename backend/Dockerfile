FROM python:3.12-slim

WORKDIR /app

# Копируем requirements и ставим зависимости (включая gunicorn)
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

# Копируем весь код проекта
COPY . .

# Миграции и запуск
CMD sh -c "python manage.py migrate --noinput && gunicorn backend.wsgi:application --bind 0.0.0.0:8000"

