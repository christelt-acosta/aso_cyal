# Análisis de Redes - Proyecto

## Introducción

La finalidad de este script es realizar un análisis de una red local para detectar los equipos conectados, identificar los puertos abiertos y tratar de obtener el sistema operativo de cada equipo.

### Funcionalidades del Script

El script realiza las siguientes tareas principales:

1. **Escaneo de la Red:**
   - Se solicita al usuario una dirección de red en formato CIDR (por ejemplo, `192.168.1.0/24`).
   - El script hace un **ping** a cada IP dentro del rango especificado para verificar cuáles están activas en la red.

2. **Detección de Puertos Abiertos:**
   - Para cada equipo activo detectado, se realiza un escaneo de puertos utilizando el comando `nc` (netcat).
   - El script verifica si los puertos especificados por el usuario están abiertos en cada equipo, y muestra el puerto junto con el servicio asociado (por ejemplo, 192.168.56.100 puerto 80 (HTTP)).

3. **Detección del Sistema Operativo:**
   - Usando el valor **TTL (Time to Live)** de la respuesta de ping, el script intenta deducir el sistema operativo del dispositivo.
     - **TTL=64** indica un sistema Linux.
     - **TTL=128** indica un sistema Windows.
   - Si el TTL no coincide con estos valores, el sistema operativo se considera desconocido.

4. **Almacenamiento de los Resultados:**
   - Toda la información, como las IPs activas, los puertos abiertos y los sistemas operativos detectados, se muestra por pantalla.
   - Los resultados también se almacenan en un archivo de texto especificado por el usuario en el script.






