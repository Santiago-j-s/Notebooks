
### 1. Enunciar las Funciones de la Capa de Red

* Se encarga de llevar paquetes de origen a destino.
* Controla de la subred, conoce su topología.
* Escoge trayectorias adecuadas.
* Controla congestión de la subred
* Maneja problemas de interconexión entre redes.


### 2. ¿Qué tipo de servicios ofrece la Capa de Red a la Capa de Transporte?

1. **Sin conexión:**
    * Sup. que tarea de subred es mover solamente paquetes con dirección de
destino completa.
    * Si la subred es inestable, los hosts deben efectuar control de errores y
flujo.

2. **Orientados a conexión:**
    * Proceso de capa de red primero debe establecer conexión (con id. especial)
con el receptor.
    * Comunicación bidireccional, con paquetes en secuencia, luego se libera
conexión.

### 3. Tachar lo que no corresponda

* **Estructura de Servicios de Red y Subredes.** <br />
    El servicio ofrecido (<strike>ES</strike>/ NO ES) independiente de la
estructura de subred, ya sea de (CIRCUITOS VIRTUALES / DATAGRAMAS /
<strike>802.3</strike>)


* Es posible la implementación de una subred de (DATAGRAMAS / SEGMENTOS) de un
servicio sin conexiones (UDP sobre IP / TCP sobre IP)

### 4. Mencionar dos Algoritmos de Enrutamiento Estáticos y dos Dinámicos.

* **Estáticos**
    * Enrutamiento por Trayectoria más Corta
    * Inundación
    * Enrutamiento basado en Flujo/Tráfico
* **Dinámicos**
    * Enrutamiento por Vector de Distancia
    * Enrutamiento por Estado de Enlace

### 5. Marcar lo que corresponda. Algoritmos de Enrutamiento Estáticos.
b, c y e

### 6. Dada la siguiente interred de 4 redes y tres routers, con dir. IP
asignada a cada interfaz de c/ router, y la tabla de ruteo del router central,
se pide realizar las tablas de los routers de los extremos. (Esquema
Enrutamiento con Salto al Siguiente. Next Hop)

#### <center>Router A</center>
  Destino    | Máscara       |  Siguiente Salto
-------------|---------------|------------------
  30.0.0.0   | 255.0.0.0     |  Entrega Directa
  40.0.0.0   | 255.0.0.0     |  Entrega Directa
  128.1.0.0  | 255.255.0.0   |  40.0.0.8
  192.4.10.0 | 255.255.255.0 |  40.0.0.8

#### <center>Router B</center>
  Destino    | Máscara       |  Siguiente Salto
-------------|---------------|------------------
  30.0.0.0   | 255.0.0.0     |  40.0.0.7
  40.0.0.0   | 255.0.0.0     |  Entrega Directa
  128.1.0.0  | 255.255.0.0   |  Entrega Directa
  192.4.10.0 | 255.255.255.0 |  128.1.0.9

#### <center>Router C</center>
  Destino    | Máscara       |  Siguiente Salto
-------------|---------------|------------------
  30.0.0.0   | 255.0.0.0     |  128.1.0.8
  40.0.0.0   | 255.0.0.0     |  128.1.0.8
  128.1.0.0  | 255.255.0.0   |  Entrega Directa
  192.4.10.0 | 255.255.255.0 |  Entrega Directa

### 7. ¿Qué niveles del modelo OSI deben preocuparse del control de congestión
en una WAN? ¿Para qué sirven los algoritmos de Control de Congestión?

* Niveles 3 y 4.

* Evitar la degradación del desempeño producida por exceso de paquetes presentes
en una subred.

### 8. ¿Para qué sirve el método de Paquetes de Estrangulamiento?

Un paquete de estrangulamiento obliga al host de origen a reducir el tráfico
envíado a un determinado destino en un determinado %. Es un método de control de
congestión.

### 9. Una computadora de una red a 6Mbps como tasa de salida, se regula
mediante una Token Bucket. La cubeta se llena a razón de 1Mbps. Inicialmente
esta llena a su capacidad máxima de 8MB. ¿Durante cuánto tiempo puede la pc
transmitir a 6Mbps?

$$ t * 6Mb/s = t * 1Mb/s + 8Mb $$

$$ t * 5Mb/s = 8Mb $$

$$ t = \dfrac{8Mb}{5Mb/s} $$

$$ t = \dfrac{8}{5}s $$

### 10. El algoritmo de Token Bucket permite las ráfagas pero hasta alguna
longitud limitada S. Si la capacidad del cubo es de 250kb, los tokens llegan a
una velocidad tal que permita salidas de 2MBps, y la velocidad de salida máxima
es de 25MBps. ¿Cuál es el tiempo de ráfaga máxima y su tamaño?

$$ t * 25MBps = t * 2MBps + 250kb $$

$$ t * 25MBps = t * 2MBps + 0.3125MB $$

$$ t * 23MBps = 0.3125MB $$

$$ t = 0.0136s $$

$$ T_{\text{ráfaga}} = 339.67 KB $$

### 11. ¿Qué tipos de dispositivos conectan dos o más redes en las distintas
capas?

  Capa | Dispositivo
-------|----------------------------
  1    | Repetidores
  2    | Bridges
  3    | Enrutadores Multiprotocolo
  4    | Pasarelas de Transporte
  5    | Pasarelas de Aplicación

### 12. ¿Qué significa el proceso de túnel en interredes?

Es un caso común de interacción de 2 redes diferentes: cuando hosts de origen y
destino están en misma clase de red pero hay red diferente en el medio.
Enrutadores multiprotocolo encapsulan y desencapsulan los paquetes. Ej: hosts en
redes LAN Ethernet y paquete que viaja a través de WAN.

### 13. Concepto de Firewall

**2 Componentes**

* Enrutadores con filtro de paquete que inspeccionan paquetes según reglas
predeterminadas que incluyen origenes y destinos aceptables y bloqueados y
acciones a tomar con paquetes que cumplan ciertos criterios.

* Pasarela de aplicación que examina mensajes a nivel de aplicación y decide
transmitirlos o descartarlos según campos de cabecera, tamaños de mensaje o
contenidos.

### 14. En la cabecera de un Datagrama IP. ¿Qué indican los campos de
direcciones de origen y destino? ¿Qué longitud tienen en IPv4? ¿Cuál es el
tamaño mínimo de cabecera IP?

* Quién es el y quien el receptor del paquete. En una red IP cada nodo tiene una
IP única que lo identifica.

* 32 bits

* 20 bytes

### 15. ¿Cómo es el formato de direcciones IP Clases A, B y C?

 Clase |     | Red      | Host
-------|-----|----------|----------
  A    | 0   | 7 bits   | 24 bits
  B    | 10  | 14 bits  | 16 bits
  C    | 110 | 21 bits  | 8 bits

### 16. ¿Qué función cumplen los Protocolos ARP y RARP en Internet?

**ARP** resuelve el problema de encontrar la dirección Ethernet correspondiente
a una IP dada.

**RARP** permite que una estación difunda su dirección Ethernet y el servidor le
responda con la IP correspondiente a esa estación.

### 17. Ventajas de IPv6 sobre IPv4

* Más flexible y eficiente que IPv4 actual. Sigue siendo compatible con resto de
protocolos.

* Direcciones de 16 bytes de longitud (128 bits)

* Simplifica cabecera con solo 7 campos (13 en IPv4). Más rápido en enrutadores.

* Mejor apoyo a opciones (campos obligatorios a opcionales).

* Mejor seguridad con verificaciones de autenticidad y confidencialidad
