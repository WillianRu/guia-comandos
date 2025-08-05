# 🐳 Docker & Docker Compose

Guía completa de comandos para contenedores Docker y orquestación con Docker Compose.

## 📚 Índice

- [🐳 Docker Básico](./docker-basico.md) - Comandos esenciales de Docker
- [🎯 Docker Compose](./docker-compose.md) - Orquestación de contenedores
- [📝 Dockerfile](./dockerfile.md) - Creación de imágenes personalizadas

## 🚀 Comandos Esenciales

### Docker Básico
```bash
# Imágenes
docker images                    # Lista imágenes
docker pull imagen              # Descarga imagen
docker rmi imagen               # Elimina imagen

# Contenedores
docker ps                       # Lista contenedores activos
docker ps -a                    # Lista todos los contenedores
docker run imagen               # Ejecuta contenedor
docker stop contenedor          # Detiene contenedor
docker rm contenedor            # Elimina contenedor
```

### Docker Compose
```bash
docker-compose up               # Levanta servicios
docker-compose up -d            # Levanta en segundo plano
docker-compose down             # Detiene y elimina
docker-compose logs             # Muestra logs
docker-compose ps               # Lista contenedores
```

## 🎯 Ejemplos Prácticos

### Desarrollo Local
```bash
# Levantar stack completo
docker-compose up -d

# Ver logs en tiempo real
docker-compose logs -f

# Ejecutar comando en contenedor
docker-compose exec app bash

# Reconstruir imagen
docker-compose build --no-cache
```

### Producción
```bash
# Usar archivo específico
docker-compose -f docker-compose.prod.yml up -d

# Escalar servicios
docker-compose up -d --scale web=3

# Backup de volúmenes
docker run --rm -v proyecto_db:/data -v $(pwd):/backup alpine tar czf /backup/backup.tar.gz -C /data .
```

## 📁 Estructura Típica

```
proyecto/
├── docker-compose.yml          # Configuración principal
├── docker-compose.dev.yml      # Configuración desarrollo
├── docker-compose.prod.yml     # Configuración producción
├── Dockerfile                  # Imagen de aplicación
├── .dockerignore              # Archivos a ignorar
└── docker/
    ├── nginx/
    │   ├── Dockerfile
    │   └── nginx.conf
    └── postgres/
        └── init.sql
```

## 💡 Mejores Prácticas

### Seguridad
- No ejecutes contenedores como root
- Usa imágenes oficiales cuando sea posible
- Escanea imágenes en busca de vulnerabilidades
- Mantén imágenes actualizadas

### Rendimiento
- Usa `.dockerignore` para excluir archivos innecesarios
- Optimiza capas en Dockerfile
- Usa volúmenes para datos persistentes
- Limpia imágenes no utilizadas

### Desarrollo
- Usa `docker-compose` para desarrollo local
- Configura hot-reload cuando sea posible
- Usa variables de entorno para configuración
- Documenta comandos comunes

## 🔧 Comandos de Diagnóstico

### Información del Sistema
```bash
docker info                      # Información del daemon
docker system df                 # Uso de espacio
docker system prune              # Limpia recursos no utilizados
```

### Inspección de Contenedores
```bash
docker inspect contenedor        # Información detallada
docker logs contenedor           # Logs del contenedor
docker exec -it contenedor bash  # Acceso interactivo
```

## 📖 Recursos Adicionales

- [Docker Documentation](https://docs.docker.com/)
- [Docker Compose Documentation](https://docs.docker.com/compose/)
- [Docker Hub](https://hub.docker.com/)
- [Docker Best Practices](https://docs.docker.com/develop/dev-best-practices/)

---

*Basado en la guía de @midudev* 