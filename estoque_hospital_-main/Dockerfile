FROM python:3.11-slim

# Instalar dependências do sistema necessárias para psycopg2
RUN apt-get update && apt-get install -y \
    libpq-dev \
    gcc \
    python3-dev \
    build-essential \
    && rm -rf /var/lib/apt/lists/*

WORKDIR /app

# Copiar e instalar dependências Python
COPY requirements.txt .
RUN pip install --upgrade pip setuptools wheel
RUN pip install --no-cache-dir -r requirements.txt

# Copiar o restante do código
COPY . .

EXPOSE 8000

# Se for Flask
CMD ["python", "app.py"]

# Se for Django, substitua por:
# CMD ["gunicorn", "estoque_hospital.wsgi:application", "--bind", "0.0.0.0:8000"]
