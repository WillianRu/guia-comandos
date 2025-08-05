# 🌐 Comandos de Red

Guía completa de comandos para diagnóstico, configuración y monitoreo de redes.

## 📚 Índice

- [🔍 Diagnóstico](./comandos.md) - Comandos para diagnosticar problemas de red
- [⚙️ Configuración](./configuracion.md) - Configuración de interfaces y servicios

## 🚀 Comandos Esenciales

### Diagnóstico de Conectividad
```bash
ping dominio.com              # Prueba conectividad básica
ping -c 4 8.8.8.8            # Ping con límite de paquetes
ping -i 0.2 google.com        # Ping con intervalo específico
```

### Información de Red
```bash
ip addr                       # Muestra direcciones IP
ip route                      # Muestra tabla de rutas
ip link                       # Muestra interfaces de red
```

### Puertos y Servicios
```bash
netstat -tuln                 # Puertos abiertos
ss -tuln                      # Versión moderna de netstat
lsof -i                       # Procesos usando puertos
```

## 🎯 Ejemplos Prácticos

### Diagnóstico de Problemas
```bash
# Verificar conectividad
ping google.com

# Verificar resolución DNS
nslookup google.com
dig google.com

# Verificar puertos específicos
telnet google.com 80
nc -zv google.com 80

# Verificar ruta
traceroute google.com
```

### Monitoreo de Red
```bash
# Ver estadísticas de red
netstat -i                    # Interfaces
netstat -s                    # Estadísticas generales
ss -s                         # Estadísticas de sockets

# Monitoreo en tiempo real
iftop                         # Uso de ancho de banda
nethogs                       # Uso por proceso
```

## 💡 Comandos Avanzados

### Análisis de Tráfico
```bash
tcpdump -i eth0              # Captura paquetes
tcpdump port 80               # Solo puerto 80
tcpdump host 192.168.1.1     # Solo host específico
wireshark                     # Interfaz gráfica para análisis
```

### Configuración de Red
```bash
# Configurar IP estática
ip addr add 192.168.1.100/24 dev eth0

# Agregar ruta
ip route add default via 192.168.1.1

# Configurar DNS
echo "nameserver 8.8.8.8" >> /etc/resolv.conf
```

## 🔧 Comandos de Diagnóstico

### Información del Sistema
```bash
hostname                      # Nombre del host
domainname                    # Dominio del sistema
dnsdomainname                 # Dominio DNS

# Información detallada
cat /etc/hosts               # Archivo hosts local
cat /etc/resolv.conf         # Configuración DNS
```

### Herramientas de Red
```bash
# Herramientas de diagnóstico
mtr google.com               # Traceroute mejorado
nmap localhost               # Escaneo de puertos
nmap -sP 192.168.1.0/24     # Escaneo de red

# Herramientas de transferencia
wget url                     # Descarga archivo
curl url                     # Petición HTTP
scp archivo usuario@host:/ruta # Copia segura
```

## ⚠️ Consejos de Seguridad

### Monitoreo
- Usa `netstat` para detectar conexiones sospechosas
- Monitorea puertos abiertos regularmente
- Verifica logs de firewall
- Usa herramientas como `fail2ban`

### Configuración
- Cambia puertos por defecto
- Usa firewalls apropiados
- Configura VPN cuando sea necesario
- Mantén sistemas actualizados

## 📖 Recursos Adicionales

- [Linux Network Administration](https://tldp.org/LDP/nag2/)
- [Wireshark Documentation](https://www.wireshark.org/docs/)
- [Nmap Documentation](https://nmap.org/docs.html)
- [TCP/IP Illustrated](https://en.wikipedia.org/wiki/TCP/IP_Illustrated)

---

*Basado en la guía de @midudev* 