# ACI606 - Docker Rescue Challenge

Aplicación web multi-servicio contenerizada compuesta por Frontend (Nginx), Backend/API (FastAPI) y Base de Datos (PostgreSQL).

## Arquitectura
Cliente -> Frontend (Nginx :8080 -> :80) -> Backend (FastAPI :8000) -> Database (PostgreSQL :5432 + volumen pgdata)

## Requisitos previos
- Docker y Docker Compose v2 operativos.
- Archivo .env configurado a partir de .env.example:

    cp .env.example .env

## Procedimiento de operación

### 1. Construir e iniciar la solución
    docker compose up --build -d

### 2. Verificar estado de los servicios y salud
    docker compose ps
    curl -i http://127.0.0.1:8080/api/health

### 3. Consultar logs de diagnóstico
    docker compose logs -f

### 4. Detener los servicios (conservando datos persistentes)
    docker compose down

### 5. Recrear la solución limpia
    docker compose up --build -d
