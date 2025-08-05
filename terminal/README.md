# 🖥️ Comandos de Terminal

Guía completa de comandos de línea de comandos para navegación, gestión de archivos y administración del sistema.

## 📚 Índice

- [📁 Navegación](#-navegación) - Comandos para moverse por el sistema de archivos
- [📄 Gestión de Archivos](#-gestión-de-archivos) - Crear, copiar, mover y eliminar archivos
- [🔒 Permisos](#-permisos) - Gestión de permisos y propietarios
- [⚙️ Procesos](#️-procesos) - Administración de procesos del sistema

## 📁 Navegación

Comandos esenciales para moverse por el sistema de archivos y explorar directorios.

### Comandos Básicos

#### `pwd` - Print Working Directory
```bash
pwd
# Ejemplo: /home/usuario/proyectos
```
**Descripción**: Muestra la ruta completa del directorio actual.

#### `ls` - List
```bash
ls                    # Lista archivos básicos
ls -la               # Lista todos los archivos (incluyendo ocultos)
ls -lh               # Lista con tamaños legibles
ls -lt               # Lista ordenado por fecha (más reciente primero)
ls -R                # Lista recursivamente (subdirectorios)
```
**Descripción**: Lista archivos y carpetas del directorio actual.

#### `cd` - Change Directory
```bash
cd                    # Va al directorio home
cd /ruta/completa    # Va a una ruta específica
cd ..                 # Sube un nivel
cd ../..              # Sube dos niveles
cd -                  # Va al directorio anterior
cd ~                  # Va al directorio home
```
**Descripción**: Cambia el directorio de trabajo actual.

#### `tree` - Tree Structure
```bash
tree                  # Muestra estructura completa
tree -L 2            # Limita a 2 niveles de profundidad
tree -d              # Solo muestra directorios
tree -I "node_modules" # Ignora carpetas específicas
```
**Descripción**: Muestra la estructura de directorios en forma de árbol.

### Ejemplos Prácticos de Navegación

#### Navegación Rápida
```bash
# Ir al directorio de proyectos
cd ~/proyectos

# Ver qué hay en el directorio
ls -la

# Ver la estructura del proyecto
tree -L 3

# Volver al directorio anterior
cd -
```

#### Exploración de Sistema
```bash
# Ver directorio actual
pwd

# Listar archivos del sistema
ls /etc

# Ver estructura de /var
tree /var -L 2
```

### Trucos Útiles de Navegación

#### Autocompletado
- Presiona `Tab` para completar nombres de archivos/directorios
- Presiona `Tab` dos veces para ver opciones disponibles

#### Navegación Rápida
```bash
# Crear alias para directorios frecuentes
alias proj="cd ~/proyectos"
alias docs="cd ~/documentos"

# Usar variables de entorno
cd $HOME
cd $PWD
```

#### Búsqueda de Directorios
```bash
# Buscar directorio por nombre
find / -type d -name "nombre_directorio" 2>/dev/null

# Buscar en directorio actual
find . -type d -name "nombre"
```

### Comandos Relacionados con Navegación
```bash
pushd /popd          # Pila de directorios
dirs                  # Muestra pila de directorios
realpath              # Muestra ruta absoluta
basename /dirname     # Extrae nombre de archivo/directorio
```

## 📄 Gestión de Archivos

### Comandos Básicos
```bash
touch        # Crea archivo vacío
mkdir        # Crea directorio
cp           # Copia archivos
mv           # Mueve/renombra archivos
rm           # Elimina archivos
```

### Lectura de Archivos
```bash
cat          # Muestra contenido completo
less         # Visualiza página por página
head         # Primeras líneas
tail         # Últimas líneas
```