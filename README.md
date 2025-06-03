Sistema Distribuido con Microservicios usando ZeroMQ y Docker
Este proyecto simula un sistema de monitoreo ambiental distribuido compuesto por sensores de humo, humedad y temperatura, además de un aspersor, un servidor central de recolección de datos y un proxy (broker) que gestiona la comunicación entre ellos utilizando ZeroMQ.
Despliegue del Sistema

1. Requisitos
Asegúrate de tener instalados en tu sistema:
- Docker
- Docker Compose

2. Construcción y ejecución de los contenedores
Ejecuta los siguientes comandos desde la raíz del proyecto para desplegar los contenedores (estos ya estan creados en el proyecto):

docker-compose down -v --remove-orphans
docker-compose up --build

Este comando:
- Detiene y elimina contenedores antiguos.
- Construye las imágenes desde los Dockerfile.
- Levanta todo el sistema.

3. Verificación (Opcional)
Puedes monitorear los logs en tiempo real con:

docker-compose logs -f

Deberías ver mensajes como:
- "Se envió el mensaje al proxy ..."
- "Reporte de temperatura ..."
- "ALERTA! ASPERSOR ENCENDIDO"
- "La temperatura promedio es: ..."

4. Apagar el sistema
- docker-compose down -v
