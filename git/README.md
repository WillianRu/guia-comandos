# 🔧 Git

Guía completa de comandos Git para control de versiones y colaboración en proyectos.

## 📚 Índice

- [🚀 Git Básico](./basico.md) - Comandos esenciales para empezar
- [⚡ Git Avanzado](./avanzado.md) - Comandos avanzados y flujos de trabajo

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

## 💡 Mejores Prácticas

### Commits
- Usa mensajes descriptivos y claros
- Un commit por cambio lógico
- Usa el imperativo: "Add", "Fix", "Update"
- Incluye contexto cuando sea necesario

### Ramas
- `main` o `master` para código estable
- `develop` para desarrollo
- `feature/` para nuevas funcionalidades
- `hotfix/` para correcciones urgentes

### Colaboración
- Siempre hace `pull` antes de `push`
- Usa Pull Requests para revisión
- Mantén ramas actualizadas
- Comunica cambios importantes

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

## 📖 Recursos Adicionales

- [Git Documentation](https://git-scm.com/doc)
- [GitHub Guides](https://guides.github.com/)
- [Git Cheat Sheet](https://education.github.com/git-cheat-sheet-education.pdf)
- [Conventional Commits](https://www.conventionalcommits.org/)

---

*Basado en la guía de @midudev* 