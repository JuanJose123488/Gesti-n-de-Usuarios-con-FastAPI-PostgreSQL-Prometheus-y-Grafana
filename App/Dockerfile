# Imagen base ligera con Python 3.12
FROM python:3.12-slim

# Evita buffering de logs y asegura salida inmediata en consola
ENV PYTHONUNBUFFERED=1

# Define el directorio de trabajo
WORKDIR /app

# Copia solo los requerimientos primero (mejor caché)
COPY requirements.txt .

# Instala dependencias
RUN pip install --no-cache-dir -r requirements.txt

# Copia el resto del código
COPY . .

# Expone el puerto 8000
EXPOSE 8000

# Comando para iniciar FastAPI con Uvicorn
CMD ["uvicorn", "main:app", "--host", "0.0.0.0", "--port", "8000"]
