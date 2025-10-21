FROM python:3.12

# Установка setuptools который включает distutils
RUN pip install --upgrade setuptools

WORKDIR /app

RUN pip install gunicorn==23.0.0

COPY requirements.txt .
RUN pip install -r requirements.txt --no-cache-dir

COPY . .

CMD ["gunicorn", "--bind", "0.0.0.0:8000", "backend.wsgi"]