# Middleware Hospitalario V3 - Render

Esta versión convierte el middleware hospitalario en una API REST desplegable en Render.

## Arquitectura

Hoppscotch -> HTTPS -> Middleware Flask en Render -> Laboratorio / Facturación simulados

## Archivos

- app.py: aplicación Flask.
- requirements.txt: dependencias.
- render.yaml: configuración opcional de infraestructura para Render.
- .gitignore: archivos que no deben subirse.
- ejemplos/: JSON de prueba.

## Endpoints

GET /
POST /login
POST /middleware

## Variables de entorno

JWT_SECRET
HOSPITAL_USER
HOSPITAL_PASSWORD

Valores didácticos sugeridos:

HOSPITAL_USER = hospital
HOSPITAL_PASSWORD = 1234

JWT_SECRET debe ser una cadena secreta. En producción nunca debe publicarse.

## Comandos de Render

Build Command:
pip install -r requirements.txt

Start Command:
gunicorn app:app

## Prueba

1. POST /login con login.json.
2. Copiar token.
3. POST /middleware con Authorization: Bearer TOKEN.
4. Usar laboratorio.json o facturacion.json.
