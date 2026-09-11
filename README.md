# Laboratorio 02
Hoy utilizaremos docker compose para poder desplegar su trabajo. Servicio web y una
base de datos
## Stack
API
- Minimal API
- Debe retornar un mensaje incluyendo mi nombre
- Docker
- docker run -d --rm -p 3000:3000 nmatsui/hello-world-api. 5247b12cb384 relaxed_grothendieck
- docker run -d --rm -p 3001:3000 nmatsui/hello-world-api d4682f0cb8fd intelligent_boyd
- docker run -d --rm -p 3002:3000 nmatsui/hello-world-api 40a07011bd49 wonderful_wu
BD
- PostgreSQL
- $ docker run --name some-postgres -e POSTGRES_PASSWORD=mysecretpassword -d
postgres
# Indicaciones
## Comandos
```bash
docker compose up -d
```
## Configuración por entorno
```
MESSAGE=<Colocar nombre>
```
# Creditos
- Steffano Alessandro Ventura Florian
# ETC