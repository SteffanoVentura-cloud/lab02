# Laboratorio 02 

## Descripción

Este proyecto consiste en el despliegue de una aplicación utilizando Docker Compose.

La solución está compuesta por servicios API y una base de datos PostgreSQL, utilizando contenedores Docker, variables de entorno, volúmenes y redes personalizadas.

---

# Arquitectura del proyecto

El proyecto contiene los siguientes servicios:

## API

Se desplegaron 3 instancias de la API:

Servicio  Puerto api_3000  3000  api_3001  3001  api_3002  3002 

Cada API retorna un mensaje configurado mediante variables de entorno.

Ejemplo de respuesta:

```json
{
  "mensaje": "Hola soy Steffano, API funcionando correctamente"
}
```

---

## Base de Datos

Motor utilizado:

- PostgreSQL 16

La base de datos se ejecuta dentro de un contenedor Docker y utiliza un volumen para mantener la información persistente.

---

# Tecnologías utilizadas

- Node.js
- Express
- PostgreSQL
- Docker
- Docker Compose

---

# Estructura del proyecto

```
Lab02
│
├── Api
│   ├── Dockerfile
│   ├── package.json
│   └── server.js
│
├── .env
├── .env.example
├── .gitignore
├── docker-compose.yml
└── README.md
```

---

# Configuración mediante variables de entorno

El proyecto utiliza variables de entorno mediante el archivo `.env`.

Variables utilizadas:

```env
MESSAGE=Hola soy Steffano, API funcionando correctamente

POSTGRES_USER=usuario
POSTGRES_PASSWORD=password
POSTGRES_DB=lab02
```

Estas variables permiten configurar la aplicación sin modificar el código fuente.

---

# Ejecución del proyecto

## Construcción de imágenes

Para construir las imágenes Docker:

```bash
docker compose build
```

---

## Iniciar los servicios

Para levantar todos los contenedores:

```bash
docker compose up
```

También puede ejecutarse en segundo plano:

```bash
docker compose up -d
```

---

## Detener los servicios

```bash
docker compose down
```

---

# Endpoints disponibles

La API puede ser consultada mediante:
http://localhost:3000
http://localhost:3001
http://localhost:3002
```

Respuesta esperada:

```json
{
  "mensaje": "Hola soy Steffano, API funcionando correctamente"
}
```
---

# Volúmenes Docker
Se utiliza un volumen para almacenar los datos de PostgreSQL y evitar la pérdida de información cuando el contenedor se reinicia.
Volumen utilizado:
```
lab02_postgres_data
```

Comando para verificar volúmenes:

```bash
docker volume ls
```

---

# Redes Docker

Los servicios se comunican mediante una red personalizada creada por Docker Compose.

Red utilizada:

```
lab02_red-lab
```

Comando para verificar redes:

```bash
docker network ls
```

---

# Contenedores desplegados

Servicios activos:

```
api_3000
api_3001
api_3002
postgres_lab02
```

Para verificar los contenedores:

```bash
docker ps
```

---

# Git y Conventional Commits

Los cambios del proyecto se gestionan utilizando Git siguiendo Conventional Commits.

Ejemplos:

```
feat: agregar configuracion docker compose
fix: corregir variable de entorno del mensaje
docs: actualizar README
```

---

# Autor

Steffano Alessandro Ventura Florian