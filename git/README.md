# 🔧 Git

Guía completa de comandos Git para control de versiones y colaboración en proyectos.

## 🚀 Comandos Esenciales

### Configuración Inicial
```bash
git config --global user.name "Tu Nombre"
git config --global user.email "tu@email.com"
git init                        # Inicializa repositorio
git clone url                   # Clona repositorio
```

### Flujo Básico
```bash
git add archivo                 # Añade archivo al staging
git add .                       # Añade todos los cambios
git commit -m "mensaje"         # Crea commit
git push                        # Sube cambios al remoto
git pull                        # Descarga cambios del remoto
```

### Información
```bash
git status                      # Estado del repositorio
git log                         # Historial de commits
git diff                        # Diferencias en archivos
git branch                      # Lista ramas
```

## 🎯 Flujos de Trabajo Comunes

### Desarrollo Individual
```bash
# Crear nueva rama
git checkout -b feature/nueva-funcionalidad

# Hacer cambios y commit
git add .
git commit -m "Agrega nueva funcionalidad"

# Subir cambios
git push origin feature/nueva-funcionalidad
```

### Colaboración
```bash
# Actualizar repositorio local
git pull origin main

# Crear rama para feature
git checkout -b feature/colaboracion

# Trabajar y hacer commits
git add .
git commit -m "Implementa feature"

# Subir y crear Pull Request
git push origin feature/colaboracion
```

## 🔧 Comandos de Diagnóstico

### Estado del Repositorio
```bash
git status                      # Estado general
git status --porcelain          # Formato compacto
git log --oneline               # Historial compacto
git log --graph                 # Historial con gráfico
```

### Información Detallada
```bash
git show commit                 # Detalles de un commit
git blame archivo               # Quién modificó qué línea
git diff HEAD~1                 # Diferencias con commit anterior
git remote -v                   # Repositorios remotos
```