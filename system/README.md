# ⚙️ Comandos del Sistema

Guía completa de comandos para administración y monitoreo del sistema operativo.

## 📚 Índice

- [🔧 Administración](./administracion.md) - Comandos de administración del sistema
- [📊 Monitoreo](./monitoreo.md) - Monitoreo de recursos y procesos

## 🚀 Comandos Esenciales

### Información del Sistema
```bash
uname -a                      # Información del kernel
cat /etc/os-release           # Información del sistema operativo
hostnamectl                   # Información del host
uptime                        # Tiempo de actividad
```

### Procesos y Recursos
```bash
top                           # Procesos en tiempo real
htop                          # Versión mejorada de top
ps aux                        # Lista todos los procesos
free -h                       # Memoria disponible
df -h                         # Espacio en disco
```

### Usuarios y Permisos
```bash
who                           # Usuarios conectados
w                             # Información detallada de usuarios
id                            # Información del usuario actual
sudo                          # Ejecutar como superusuario
su                            # Cambiar de usuario
```

## 🎯 Ejemplos Prácticos

### Monitoreo del Sistema
```bash
# Ver uso de CPU y memoria
top -n 1

# Ver procesos ordenados por CPU
ps aux --sort=-%cpu | head -10

# Ver procesos ordenados por memoria
ps aux --sort=-%mem | head -10

# Ver espacio en disco
df -h | grep -E '^/dev/'

# Ver memoria detallada
cat /proc/meminfo
```

### Administración de Servicios
```bash
# Servicios systemd
systemctl status servicio     # Estado del servicio
systemctl start servicio      # Iniciar servicio
systemctl stop servicio       # Detener servicio
systemctl restart servicio    # Reiniciar servicio
systemctl enable servicio     # Habilitar al inicio
systemctl disable servicio    # Deshabilitar al inicio

# Servicios tradicionales
service servicio status       # Estado del servicio
service servicio start        # Iniciar servicio
service servicio stop         # Detener servicio
```

## 💡 Comandos Avanzados

### Análisis de Logs
```bash
# Ver logs del sistema
journalctl                    # Logs de systemd
tail -f /var/log/syslog      # Seguir logs en tiempo real
grep ERROR /var/log/syslog    # Buscar errores

# Logs específicos
tail -f /var/log/apache2/access.log  # Logs de Apache
tail -f /var/log/nginx/access.log    # Logs de Nginx
```

### Gestión de Paquetes
```bash
# Debian/Ubuntu
apt update                    # Actualizar lista de paquetes
apt upgrade                   # Actualizar paquetes
apt install paquete          # Instalar paquete
apt remove paquete           # Desinstalar paquete

# Red Hat/CentOS
yum update                    # Actualizar paquetes
yum install paquete          # Instalar paquete
yum remove paquete           # Desinstalar paquete

# Arch Linux
pacman -Syu                  # Actualizar sistema
pacman -S paquete            # Instalar paquete
pacman -R paquete            # Desinstalar paquete
```

## 🔧 Comandos de Diagnóstico

### Hardware
```bash
lscpu                        # Información de CPU
lshw                         # Información de hardware
lsblk                        # Dispositivos de bloque
fdisk -l                     # Particiones de disco
```

### Red
```bash
ip addr                      # Direcciones IP
ip route                     # Tabla de rutas
ss -tuln                     # Puertos abiertos
netstat -i                   # Interfaces de red
```

### Rendimiento
```bash
iostat                       # Estadísticas de I/O
vmstat                       # Estadísticas de memoria virtual
mpstat                       # Estadísticas de CPU múltiple
sar                          # Estadísticas del sistema
```

## ⚠️ Comandos de Emergencia

### Recuperación
```bash
# Modo de recuperación
systemctl rescue              # Modo rescate
systemctl emergency           # Modo emergencia

# Recuperar contraseña root
passwd root                   # Cambiar contraseña root

# Recuperar GRUB
grub-install /dev/sda        # Reinstalar GRUB
update-grub                   # Actualizar configuración GRUB
```

### Limpieza del Sistema
```bash
# Limpiar caché de paquetes
apt clean                    # Debian/Ubuntu
yum clean all                # Red Hat/CentOS

# Limpiar logs antiguos
journalctl --vacuum-time=7d  # Limpiar logs de más de 7 días

# Limpiar archivos temporales
rm -rf /tmp/*                # Limpiar directorio temporal
```

## 📖 Recursos Adicionales

- [Linux System Administration](https://tldp.org/LDP/sag/)
- [Systemd Documentation](https://www.freedesktop.org/wiki/Software/systemd/)
- [Linux Performance](http://www.brendangregg.com/linuxperf.html)
- [Linux Command Library](https://linuxcommandlibrary.com/)

---

*Basado en la guía de @midudev* 