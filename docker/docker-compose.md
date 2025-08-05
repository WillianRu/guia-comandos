# 🎯 Docker Compose

Los 10 comandos esenciales de Docker Compose para orquestar contenedores.

## 🚀 Comandos Esenciales

### 1. **Levanta los servicios definidos en el archivo**
```bash
docker-compose up
```
**Descripción**: Crea y arranca todos los servicios definidos en `docker-compose.yml`.

### 2. **Levanta los servicios en segundo plano (detached)**
```bash
docker-compose up -d
```
**Descripción**: Ejecuta los servicios en modo daemon (background).

### 3. **Detiene y elimina contenedores, redes y volúmenes**
```bash
docker-compose down
```
**Descripción**: Para todos los servicios y limpia recursos creados.

### 4. **Construye las imágenes de los servicios**
```bash
docker-compose build
```
**Descripción**: Construye las imágenes especificadas en el Dockerfile de cada servicio.

### 5. **Reinicia todos los servicios**
```bash
docker-compose restart
```
**Descripción**: Reinicia todos los servicios sin recrear contenedores.

### 6. **Detiene los servicios sin eliminar contenedores**
```bash
docker-compose stop
```
**Descripción**: Para los servicios pero mantiene contenedores y volúmenes.

### 7. **Inicia servicios previamente detenidos**
```bash
docker-compose start
```
**Descripción**: Arranca servicios que fueron detenidos con `stop`.

### 8. **Lista los contenedores en ejecución**
```bash
docker-compose ps
```
**Descripción**: Muestra el estado de todos los servicios del proyecto.

### 9. **Muestra los logs de todos los servicios**
```bash
docker-compose logs
```
**Descripción**: Muestra los logs combinados de todos los servicios.

### 10. **Ejecuta un comando dentro de un contenedor**
```bash
docker-compose exec <servicio> <comando>
```
**Descripción**: Ejecuta un comando específico en un servicio en ejecución.

## 🎯 Ejemplos Prácticos

### Desarrollo Local
```bash
# Levantar stack completo en background
docker-compose up -d

# Ver logs en tiempo real
docker-compose logs -f

# Ejecutar migraciones en la base de datos
docker-compose exec db psql -U usuario -d base_datos -f migrations.sql

# Reconstruir solo un servicio
docker-compose build --no-cache app

# Reiniciar solo un servicio
docker-compose restart web
```

### Producción
```bash
# Usar archivo de producción
docker-compose -f docker-compose.prod.yml up -d

# Escalar servicios
docker-compose up -d --scale web=3 --scale worker=2

# Backup de volúmenes
docker-compose exec db pg_dump -U usuario base_datos > backup.sql
```

## 📁 Archivo docker-compose.yml Ejemplo

```yaml
version: '3.8'

services:
  web:
    build: .
    ports:
      - "3000:3000"
    environment:
      - NODE_ENV=development
    volumes:
      - .:/app
      - /app/node_modules
    depends_on:
      - db

  db:
    image: postgres:13
    environment:
      - POSTGRES_DB=myapp
      - POSTGRES_USER=usuario
      - POSTGRES_PASSWORD=password
    volumes:
      - postgres_data:/var/lib/postgresql/data
    ports:
      - "5432:5432"

  redis:
    image: redis:alpine
    ports:
      - "6379:6379"

volumes:
  postgres_data:
```

## 💡 Comandos Adicionales Útiles

### Gestión de Servicios
```bash
# Ver estado detallado
docker-compose ps -a

# Ver logs de un servicio específico
docker-compose logs web

# Seguir logs en tiempo real
docker-compose logs -f web

# Ejecutar comando en servicio no iniciado
docker-compose run --rm app npm test

# Escalar servicios
docker-compose up -d --scale web=3
```

### Gestión de Imágenes
```bash
# Construir sin cache
docker-compose build --no-cache

# Construir solo un servicio
docker-compose build web

# Forzar reconstrucción
docker-compose build --force-rm
```

### Limpieza
```bash
# Eliminar contenedores, redes y volúmenes
docker-compose down -v

# Eliminar también imágenes
docker-compose down --rmi all

# Limpiar volúmenes no utilizados
docker volume prune
```

## ⚠️ Consejos Importantes

### Rendimiento
- Usa `docker-compose up -d` para desarrollo
- Configura volúmenes para datos persistentes
- Usa `.dockerignore` para optimizar builds

### Debugging
- Usa `docker-compose logs -f` para monitorear
- Ejecuta `docker-compose exec` para debugging interactivo
- Verifica estado con `docker-compose ps`

### Producción
- Usa archivos específicos para producción
- Configura variables de entorno
- Implementa health checks
- Usa restart policies apropiadas

## 🔧 Comandos de Diagnóstico

```bash
# Ver configuración
docker-compose config

# Ver diferencias
docker-compose diff

# Ver uso de recursos
docker-compose top

# Ver información de red
docker-compose network ls
```

---

*Basado en la guía de @midudev* 