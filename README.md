# Examen_Redes_II

# REDES

# Parte I: Conceptos y Teoría

## 1. El Mural de las Siete Capas

### ¿Qué representa el mural de las siete capas en términos de las redes de comunicación modernas?
El Mural de las Siete Capas representa el Modelo OSI (Open Systems Interconnection), una estructura conceptual que describe cómo se comunican los sistemas de red en el mundo moderno. En términos de redes de comunicación actuales, este "mural" es un mapa ancestral que nos guía en la interacción de dispositivos y protocolos, asegurando la interoperabilidad y el correcto flujo de datos a través de infraestructuras digitales.

### Identificación de las siete capas

| Capa | Descripción | Ejemplo de Protocolos/Dispositivos |
|------|-------------|------------------------------------|
| **Capa 7 - Aplicación** | Interfaz entre el usuario y la red. Proporciona servicios de red a las aplicaciones. | HTTP, FTP, SMTP, DNS, Telnet |
| **Capa 6 - Presentación** | Se encarga del formato, cifrado y compresión de datos para su correcta interpretación. | SSL/TLS, JPEG, GIF, ASCII, MPEG |
| **Capa 5 - Sesión** | Gestiona las sesiones de comunicación entre dispositivos. | NetBIOS, RPC, PPTP |
| **Capa 4 - Transporte** | Garantiza la entrega confiable de datos, segmentación y control de flujo. | TCP, UDP |
| **Capa 3 - Red** | Determina la ruta que deben seguir los datos entre origen y destino. | IP, ICMP, RIP, OSPF, Routers |
| **Capa 2 - Enlace de Datos** | Controla el acceso al medio y la detección de errores en la transmisión. | Ethernet, MAC, ARP, Switches |
| **Capa 1 - Física** | Transmite los bits a través del medio físico (cableado, radiofrecuencia, fibra óptica). | Cables, Wi-Fi, Bluetooth, Hub |

### Relación de este modelo con el proceso de comunicación de datos actual

| Característica | **Modelo OSI** | **Modelo TCP/IP** |
|----------------|----------------|-------------------|
| **Número de capas** | 7 capas (Física, Enlace de datos, Red, Transporte, Sesión, Presentación y Aplicación) | 4 capas (Acceso a red, Internet, Transporte y Aplicación) |
| **Orientación** | Modelo teórico con capas bien definidas | Modelo práctico basado en protocolos usados en redes reales |
| **Capa de aplicación** | Separa la presentación y sesión | Todo se maneja dentro de la capa de aplicación |
| **Capa de transporte** | Solo soporta comunicación orientada a conexión | Soporta tanto conexión (TCP) como sin conexión (UDP) |
| **Ruteo de paquetes** | Se realiza en la capa de red | Se realiza en la capa de internet |
| **Flexibilidad** | Mayor flexibilidad para definir protocolos en cada capa | Enfocado en la eficiencia y en protocolos ya estandarizados |

### Conclusión
El modelo OSI es más estructurado y teórico, mientras que el TCP/IP es un modelo más práctico y utilizado en la actualidad.
![image](https://github.com/user-attachments/assets/84ad34dd-8265-4c9f-96b7-609d983d3fb0)



# 2. Los pergaminos del mensajero 

Los rituales descritos en los pergaminos representan dos modelos fundamentales de transmisión de datos en redes modernas:

### 1. El Ritual del Mensajero Confiable
Equivale al protocolo TCP (Transmission Control Protocol).
- El saludo de tres pasos representa el **Three-Way Handshake**, donde el emisor y el receptor establecen una conexión antes de transmitir datos.
- La confirmación de recibido simboliza los **ACK** (Acknowledgements), asegurando que los datos llegaron correctamente.
- La retransmisión en caso de fallo refleja los mecanismos de control de errores y reenvío de paquetes perdidos en TCP.

### 2. El Ritual del Mensajero Veloz
Se asocia con **UDP** (User Datagram Protocol).
- No hay un saludo previo, lo que indica que UDP no establece conexión antes de enviar los datos.
- Los mensajes se envían continuamente sin confirmar su recepción, reflejando la naturaleza no confiable pero rápida de UDP.
- Aunque algunos mensajes puedan perderse, la velocidad es la prioridad, lo que lo hace ideal para aplicaciones en tiempo real como **VoIP**, **streaming** y **videojuegos en línea**.

---

## Pregunta 3: TCP vs. UDP

| Característica    | **TCP (Transmission Control Protocol)** | **UDP (User Datagram Protocol)** |
|-------------------|----------------------------------------|---------------------------------|
| **Orientación**    | Orientado a conexión                   | No orientado a conexión        |
| **Fiabilidad**     | Confiable (usa acuses de recibo y retransmisiones) | No confiable (sin acuses de recibo) |
| **Orden de datos** | Garantiza que los datos lleguen en orden | No garantiza el orden de llegada |
| **Velocidad**      | Más lento debido al control de errores | Más rápido, pero sin control de errores |
| **Ejemplos de uso**| Descarga de archivos, correo electrónico, navegación web | Streaming de video/audio, videollamadas, juegos en línea |

![image](https://github.com/user-attachments/assets/baffbf65-bb8a-4c0c-9caf-1a8733d1f95b)

# 3. El Enigma de las Subredes

El enigma de la losa es un desafío clásico que nos invita a desentrañar las antiguas técnicas de **subnetting** para dividir redes en subredes más pequeñas, algo que aún es crucial en las modernas redes de comunicación.

## Contexto del Enigma
La antigua red usaba la dirección **192.168.50.0** como base y necesitaba dividirse en 4 subredes de igual tamaño, una para cada gremio. Para lograrlo, necesitamos conocer la máscara de subred que los antiguos guardianes de las redes habrían utilizado para dividir la red y cuántas direcciones de host (utilizables) tendría cada subred.

## Razonamiento y Cálculos

1. **Dirección base de la red**: 192.168.50.0/24  
   Esto significa que tenemos una red con una máscara de subred de **255.255.255.0**, o **/24**.

2. **Requerimiento**: Necesitamos dividir esta red en 4 subredes de igual tamaño.  
   Para ello, debemos tomar prestados bits de la parte de host de la dirección para crear más subredes.

3. **Número de subredes necesarias**:  
   Queremos 4 subredes, lo que significa que necesitamos **2 bits adicionales** para obtener 4 subredes (**2^2 = 4**).

4. **Nueva máscara de subred**:  
   Al tomar prestados 2 bits de la parte de host, la máscara original de **/24** se convierte en **/26**.  
   Esto significa que la nueva máscara es **255.255.255.192**.

5. **Número de direcciones por subred**:  
   En una subred **/26**, la cantidad total de direcciones es **2^(32-26) = 64** direcciones por subred.  
   Pero no todas son utilizables, ya que 2 direcciones son reservadas: una para la dirección de red (primera dirección) y otra para la dirección de **broadcast** (última dirección).  
   Por lo tanto, el número de direcciones de host utilizables en cada subred será **64 - 2 = 62** direcciones.

## Respuesta Final
- **Máscara de subred**: 255.255.255.192 o **/26**.  
- **Direcciones de host utilizables por subred**: **62**.

![image](https://github.com/user-attachments/assets/fe3db1c7-3d87-47c1-b630-50fab9ed81a8)

# Tabla de Enrutamiento

| **Destino de Red**   | **Máscara de Red**   | **Próximo Salto**      | **Interfaz**    |
|----------------------|----------------------|------------------------|-----------------|
| 192.168.50.0         | 255.255.255.192      | Directamente conectado | Interfaz 1      |
| 192.168.50.64        | 255.255.255.192      | Directamente conectado | Interfaz 2      |
| 192.168.50.128       | 255.255.255.192      | Directamente conectado | Interfaz 3      |
| 192.168.50.192       | 255.255.255.192      | Directamente conectado | Interfaz 4      |

# 4. La Encrucijada de las Rutas

El tótem representa un **router**, que dirige el tráfico de datos usando **rutas estáticas** y **dinámicas**.  
Las flechas fijas indican **rutas estáticas**, configuradas manualmente, mientras que las flechas móviles reflejan **rutas dinámicas**, ajustadas automáticamente según las condiciones de la red.  
Así, el router optimiza el tráfico para asegurar que los datos lleguen correctamente a su destino.

## Tabla de Enrutamiento

Una **tabla de enrutamiento** es una base de datos que un router usa para decidir el mejor camino para enviar los datos, con entradas que incluyen la red de destino, la máscara de subred, y la puerta de enlace.  
Las flechas talladas en piedra representan el **enrutamiento estático**, donde las rutas se configuran manualmente y no cambian automáticamente.  
Las flechas móviles simbolizan el **enrutamiento dinámico**, donde las rutas se actualizan automáticamente usando protocolos como **OSPF**, **EIGRP** o **RIP**, adaptándose a cambios en la red.  

En resumen, la **tabla de enrutamiento** gestiona el tráfico y las **rutas estáticas** son fijas, mientras que las **dinámicas** se ajustan automáticamente.
![image](https://github.com/user-attachments/assets/d158f37f-cd96-4e65-95d9-6a8f7f7383dc)

# 5. El Guardián de la Máscara Única

La leyenda del **Guardián de la Máscara** refleja la técnica de **NAT (Network Address Translation)** en redes modernas.  
En este caso, el guardián actúa como un intermediario que oculta las identidades de los miembros de la ciudad, utilizando su propia máscara para todas las comunicaciones externas. De manera similar, **NAT** permite que varias computadoras dentro de una red privada compartan una única dirección **IP pública** al comunicarse con el exterior.  
Cuando un paquete de datos regresa, NAT traduce la dirección de destino y lo reenvía al dispositivo correcto dentro de la red privada, manteniendo la privacidad de las direcciones internas.

## Descripción:
**NAT** es un proceso que permite que varios dispositivos dentro de una red privada compartan una única dirección **IP pública** al comunicarse con redes externas (como Internet).  
Cuando un dispositivo interno envía datos al exterior, **NAT** modifica la dirección **IP de origen** del paquete y la reemplaza con la dirección **IP pública** del router o gateway.  
Cuando la respuesta regresa, **NAT** reenvía el paquete al dispositivo interno correcto, basándose en una tabla que rastrea las conexiones activas.

## Beneficios:
1. **Conservación de direcciones IP**: NAT ayuda a preservar las direcciones **IP públicas**, permitiendo que una red interna use direcciones privadas (como las del rango **192.168.x.x**) mientras solo se necesita una **IP pública**.
2. **Seguridad**: NAT actúa como una capa adicional de **seguridad**, ocultando las direcciones internas de los dispositivos en la red privada, lo que dificulta los ataques directos desde el exterior.

![image](https://github.com/user-attachments/assets/e9fa2bd0-30a0-4cba-9e19-acd85d521afb)


# Parte II: Práctica con Cisco Packet Tracer

## Ejercicio 1: La Ruta Perdida entre Dos Reinos

La topología presentada para la resolución del ejercicio es la siguiente:
![image](https://github.com/user-attachments/assets/268b7e54-adfe-4dd4-8d0a-b2c547a31a33)

Para la correcta configuración de esta topología deberemos primero configurar correctamente los **PCs** con sus **gateways** correspondientes:

- **192.168.1.1**
- **192.168.2.1**
- **192.168.3.1**
- **192.168.4.1**

### Configuración del Router
En la configuración del router asignamos una **IP** a las interfaces que conectan con los **switches de capa 2**, que serán las **gateways** que le asignamos anteriormente a los ordenadores.

### Configuración de Rutas
Además, en la sección de **routing** añadiremos la ruta para ir de una red a otra. Para ello, crearemos otra subred (por ejemplo: **192.168.5.0/24**, que es la que se ha empleado) e indicaremos a la red a la que se desee ir y por qué dirección IP se utilizará para acceder a dicha red.

### Configuración de RIP
También tenemos que configurar el **RIP** para el servicio en la nube. Para ello, agregaremos las redes que se encuentren conectadas al router, asegurándonos de que la configuración de **RIP** permita la propagación de las rutas adecuadas entre las redes.

### Configuración de la Nube
Finalmente, para una correcta configuración de la nube, asignaremos un **número y nombre(DLCI y name)** a la interfaz en la configuración de la interfaz de la nube para que se puedan identificar correctamente las conexiones.

![image](https://github.com/user-attachments/assets/27bd3753-bb4b-447b-afbb-35b8df57c24c)
### Repetir el Proceso para la Otra Interfaz
Repetiremos el proceso de configuración en el router para la **otra interfaz** que conecta con el siguiente switch o red, asignando las direcciones IP y configurando las rutas correspondientes.

### Relación de Ambas Interfaces en Frame Relay
En el apartado de **Frame Relay**, relacionaremos ambas interfaces. Esto implica la configuración del **encapsulado** en cada interfaz, la creación de **PVCs (Permanent Virtual Circuits)** y la asignación de las **direcciones DLCI** adecuadas para establecer la comunicación entre las interfaces a través de Frame Relay.

De esta manera, ambas interfaces se conectarán y se podrán comunicar correctamente a través de la red Frame Relay.

![image](https://github.com/user-attachments/assets/215f9efd-9b83-473b-bc42-113b7e4c7658)

### Demostración de Funcionamiento de la Red

Para demostrar que la red funciona correctamente, se muestra el siguiente **ping**. Haremos ping desde un dispositivo de una red hacia un dispositivo de la otra red.
![image](https://github.com/user-attachments/assets/8f2cac81-5dcf-4bc1-be46-10def70cb82b)

### Verificación del Funcionamiento de la Red

Tal y como se muestra aquí, hemos realizado un **ping** al **192.168.3.5**, que según la topología adjuntada anteriormente se encuentra en la otra red. Por lo tanto, se verifica que se realiza el envío de paquetes a través de la nube.

A continuación, se muestra un **ping** en la misma red para verificar la conexión de dispositivos en la misma red.
![image](https://github.com/user-attachments/assets/40ad5809-9843-4cad-b37f-329224640a7c)

# Ejercicio 2: La Ciudad de las Redes Aisladas

La topología propuesta para la resolución de este ejercicio es la siguiente:
![image](https://github.com/user-attachments/assets/afbe6d90-8584-4f85-8a66-182a3169b7f5)


Para una configuración exitosa, los pasos a realizar son los siguientes:

1. **Configuración de los AP**:  
   Primero hemos configurado correctamente los **AP** asignándoles un **SSID** y una **WPA2-PSK**.

2. **Configuración de los portátiles**:  
   En los portátiles hemos añadido el módulo de conexión inalámbrica **WPN300** en la interfaz **Wireless0**.  
   Después, hemos configurado esta interfaz con el **SSID** y la **contraseña** que hemos introducido en el **AP**.

3. **Configuración de las IPs**:  
   Hemos configurado las **IP** en el apartado de **config** y en la interfaz específica que se está empleando.

4. **Configuración del Switch Central**:  
   En el **switch central**, hemos creado dos **VLAN** (VLAN 10 y VLAN 20) y hemos asignado los dispositivos a una de ellas, tal y como se muestra en el diagrama.

5. **Configuración de la Interfaz del Switch**:  
   En el **switch**, la interfaz que conecta con el router la hemos puesto en modo **trunk** y hemos añadido las VLAN creadas al **trunk** (trunk allowed).

6. **Configuración del Router**:  
   En el **router**, hemos dividido la interfaz que conecta el router con el switch en dos (si la interfaz que conecta ambos fuese la **gig0/0**, la hemos dividido en **gig0/0.10** y **gig0/0.20**).  
   A cada una le hemos asignado una **IP** y una **máscara de red**.

7. **Pruebas de Conectividad**:  
   Para probar la conectividad, realizaremos un **ping** entre VLANs y en la misma VLAN. A continuación, se adjuntan las capturas de estos pings.

Ping de una vlan a otra
![image](https://github.com/user-attachments/assets/b36e6fe8-f8be-4d0b-aaa1-a76068b409b1)

Ping entre dispositivos de la misma vlan

![image](https://github.com/user-attachments/assets/09951134-a6dd-49c9-92f4-576874d5b660)


