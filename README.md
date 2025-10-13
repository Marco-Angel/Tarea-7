# Tarea-7
Htop y arch-linux
--
## Htop
- htop es una herramienta interactiva que sirve para monitorizar los procesos y recursos del sistema en tiempo real, mucho más visual e intuitiva que top.
- Tambien, htop te dice qué está haciendo el sistema en este momento:
      -Qué procesos están activos.
      -Cuánta CPU, RAM y swap usan.
      -Qué usuarios o servicios consumen más recursos.

  <img width="1000" height="800" alt="image" src="https://github.com/user-attachments/assets/f3dfb4eb-1af3-49a1-b604-8238e98d6662" />

--
## Complementar con Glances

-glances es una herramienta más global de monitorización, que combina en una sola vista:
      -CPU, RAM, swap, red, disco, sensores, procesos, temperatura, etc.
      -Usa menos CPU que htop y ofrece una visión de todo el sistema en una sola pantalla.
- Este complementa, Procesos en detalle donde  Glances da visión de red, disco y temperatura además de CPU/RAM.
- En estado general del sistema, permite detectar cuellos de botella más rápido y exportar datos vía web o API.
<img width="1000" height="800" alt="image" src="https://github.com/user-attachments/assets/570fedde-87e5-4d2a-85dd-425884d6dc03" />

--
## Complementar con ifconfig

-ifconfig (o ip addr en sistemas modernos) muestra la configuración de las interfaces de red.
- **En que aporta**:
      - Dirección IP local (IPv4 / IPv6).
      - Máscara de red, gateway, estado de la interfaz (UP/DOWN).
      - Cantidad de paquetes transmitidos/recibidos y errores.

-**Uso conjunto**:

- htop o glances → muestran si hay carga o consumo alto de red.
- ifconfig → te deja verificar qué interfaz está activa, si hay IP asignada o pérdida de paquetes.
<img width="832" height="635" alt="image" src="https://github.com/user-attachments/assets/053f6637-6553-4abb-b036-1d7205c58b5e" />


--

## Complementar con nmap

-nmap sirve para auditar la red y los servicios expuestos, no el rendimiento del equipo.
- Descubre qué dispositivos hay en la red (nmap -sn 192.168.1.0/24).
- Lista puertos abiertos y servicios (nmap -sV 192.168.1.10).
- Detecta sistemas operativos y versiones (nmap -A).
- Brinda procesos de red sospechosos o alto tráfico, usa nmap para descubrir si el equipo está exponiendo servicios no autorizados.
- Usa la IP mostrada para definir el rango del escaneo.
<img width="914" height="630" alt="image" src="https://github.com/user-attachments/assets/737a7ee0-8061-4266-bf88-1634d0399dd7" />


--

## lynis 

lynis es una herramienta de auditoría de seguridad y cumplimiento.
Analiza configuraciones del sistema, permisos, autenticación, servicios, actualizaciones y políticas.

- Configuración del sistema operativo.
- Estado del cortafuegos y logs.
- Permisos y cuentas de usuario.
- Paquetes y actualizaciones pendientes.
- Puntuación general de seguridad.
<img width="800" height="563" alt="image" src="https://github.com/user-attachments/assets/2b233981-54ed-4dde-965e-4923e0a55dd0" />
<img width="885" height="631" alt="image" src="https://github.com/user-attachments/assets/c2c98861-b204-4f57-bd73-46494816343e" />


--

**¿Qué es IPv4?**

- IPv4 (Internet Protocol version 4) es la versión clásica del protocolo IP.
- Direcciones de 32 bits escritas en notación decimal punteada: 192.168.1.10.
- Espacio de direcciones: ~4.3 mil millones de direcciones.
- Soporta subnetting con máscara (ej. /24 → 255.255.255.0).
  
  Tipos de direcciones IPv4:

- Unicast (una sola interfaz).
- Broadcast (dirigido a todos los hosts de una red — ej. 192.168.1.255).
- Multicast (grupo de hosts — rango 224.0.0.0/4).
- Problema histórico: agotamiento de direcciones -> NAT (traducción de direcciones) muy extendido.

--

**¿Qué es IPv6?**

- IPv6 (Internet Protocol version 6) es el sucesor de IPv4.
- Direcciones de 128 bits en notación hexadecimal: 2001:0db8:85a3:0000:0000:8a2e:0370:7334.
- Notación corta: 2001:db8:85a3::8a2e:370:7334 (se comprimen ceros).
- Diseño para resolver el problema de espacio de direcciones (gran cantidad de direcciones).

Nuevas características:
- Eliminación del broadcast (usa multicast).
- Autoconfiguración (SLAAC) y DHCPv6.
- Headers simplificados para eficiencia.

Tipos de direcciones IPv6:
- Link-local: fe80::/10 (solo en enlace local, no enrutable globalmente).
- Global unicast: (p. ej. 2000::/3) — rutas públicas.
- Unique Local (ULA): fc00::/7 (equivalente privado, como RFC1918 en IPv4).


--
## Comandos útiles en Ubuntu para explorar direcciones y estado de IPv4/IPv6

- En Ubuntu moderno se recomienda usar la utilidad ip (iproute2). ifconfig todavía está presente en algunos sistemas pero está obsoleta.
  
      - Mostrar todas las direcciones (IPv4 e IPv6):

   <img width="600" height="400" alt="image" src="https://github.com/user-attachments/assets/c46057cf-c3f0-42d4-978b-e2203d0e171c" />
   <img width="700" height="400" alt="image" src="https://github.com/user-attachments/assets/28647e14-0bf6-442b-96fa-631a51f95875" />


