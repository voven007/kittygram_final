FROM python:3.9

WORKDIR /app

RUN pip install gunicorn==20.1.0

COPY requirements.txt .

RUN pip install -r requirements.txt --no-cache-dir

COPY . .

# При старте контейнера запустить сервер разработки. Old_version
# CMD ["python", "manage.py", "runserver", "0:8000"]

# При старте контейнера запустить сервер разработки. New_version
CMD ["gunicorn", "--bind", "0.0.0.0:9000", "kittygram_backend.wsgi"]