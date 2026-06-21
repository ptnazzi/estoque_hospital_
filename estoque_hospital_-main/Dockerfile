FROM python:3.11-slim

WORKDIR /app

COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

COPY . .

EXPOSE 8000

# Se for Flask
CMD ["python", "app.py"]

# Se for Django, substitua por:
# CMD ["gunicorn", "estoque_hospital.wsgi:application", "--bind", "0.0.0.0:8000"]
