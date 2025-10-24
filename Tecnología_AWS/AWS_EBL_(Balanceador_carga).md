# AWS EBL (Balanceador de carga de aws )

Balanceadores de carga 

# EBL (Elastic load balancer)
# ASG (Auto scaling group) / grupos de auto escalado.

Conocemos las capacidades de computo que podemos manejar con AWS - Instancias EC2 balanceadores de carga / lambda etc.

Tenemos que **crear una arquitectura**, necesitmos que el sistema tenga:

-  Alta disponibilidad (Catrastrofe en una zona (Natural por ejemplo))

- Eficiente : Recursos suficientes utilizados de manera correcta y no pagando en exeso. 


Como resolvemos alta disponibilidad : ``**Respaldo en varias zonas de disponibilidad** / totalmente alejadas / con comunicación y con todas las copias de mi sistema.`` Por si una zona de disponibilidad falla , en la otra se mantiene 

Como mi sistema es eficiente = : Haciendo que sea **escalable** que yo pueda **modificar los recursos en todo momento para que se modifiquen según la demanda. Que tenga mi aplicativo.

#### Puedo hacer un escalado vertical : ``Aumentar los recursos propios de una sola instancia.``
Pasa de 2 nucleos y 4 gb de ram a 4 nucleos y 16 gb de ram:

#### Puedo hacer un escalado horizontal: ``Aumentar las instnacias (duplicar maquinas) con los mismos recursos``  
Paso de 1 maquina de 2 nucleos / 4 gb ram. Paso a tener 4 maquinas de 2 nucleos /4 gb de ram.  

Si hago un escalado vertical la misma maquina va a procesar **Más peticiones por segundo** Pero esto no siempre es optimo (**El vertical**) 

Por ejemplo: Supongamos la fila de un supermercado.

- Empleado con poca experiencia / capacidad : 2 nucleos / 4 gb de ram  

Lo cambiamos por : 

- Empleado con más experiencia / capacidad :  4 nucleos / 8 gb de ram 

Pero en este ejemplo un empleado con más experiencia no será significativo el cambio porque a pesar de procesar mas rapido, el verdadero problema está en la fila , la cnatidad de productos de cada carrito, y que se está congelando la atención igual bastante tiempo. 

Es prefeible hacer un **Escalado Horizontal** 

Abrir 3 cajeros más: Para que se repartan todo el trafico de carritos de compra y atienda más peticiones. 

Entonces imaginemos un sistema que tiene ya 4 maquinas por el escalado horizontal. 

1. 1 maquina de 2 nucleos (100%)
2. 1 maquina de 2 nucleos
3. 1 maquina de 2 nucleos
4. 1 maquina de 2 nucleos

De poco o nada me sirve... Tener 4 maquinas o cajeros si todos van a la misma fila, o si todas las peiciones van a la maquina 1.

Idealmente: 

1. 1 maquina de 2 nucleos (25%)
2. 1 maquina de 2 nucleos (25%)
3. 1 maquina de 2 nucleos (25%)
4. 1 maquina de 2 nucleos (25%)

Ahora **``¿Quien decide el trafico y el destino de todas las peticiones?``** aquí es donde necesitamos un EBL (Elastic Balancer Load). **Un Balanceador de Carga** Un elemento que mueve el trafico para conseguir esta alta disponibilidad y alta eficiencia. 


## **Tipos de EBL Y ASG**

Un equilibrador de carga actúa como único punto de contacto para los clientes. El balanceador de carga distribuye el tráfico de aplicaciones entrante entre varios destinos, como EC2 instancias, en varias zonas de disponibilidad. Esto aumenta la disponibilidad de la aplicación. Puede agregar uno o varios oyentes al equilibrador de carga.

### De aplicación: 
Actua sobre la capa de la aplicación. a séptima capa del modelo de interconexión de sistemas abiertos (OSI).

Un **Application Load Balancer (ALB)** es un servicio de Amazon Elastic Load Balancing (ELB) que distribuye automáticamente el tráfico entrante (HTTP/HTTPS) entre varias instancias o contenedores. ( **``Trabaja a nivel de los protocolos./Trabaja a nivel de las peticiones/Lo que implica mayor entendimiento de las solicitudes para distribuir``** )

``Es el componente que reparte las solicitudes de los usuarios entre tus servidores (EC2, ECS, Fargate, etc.) para evitar sobrecarga y mantener alta disponibilidad.``

### De Red: 

⚙️ Qué es el Network Load Balancer

El Network Load Balancer (NLB) es un tipo de balanceador de carga de AWS que trabaja a nivel de red, es decir, en la capa 4 del modelo OSI (la capa de transporte).

Eso significa que **``no le importa qué tipo de aplicación estás ejecutando — no analiza el contenido de las solicitudes (no ve “/login” o “/api”)``**, sino que solo mira:

- La dirección IP de destino
- El puerto (por ejemplo 80, 443, 3306, etc.)
- El protocolo (TCP, UDP, TLS)

Y con esa información, reparte el tráfico entre tus servidores (instancias EC2, contenedores, etc.).

### ⚙️ Qué es el Gateway Load Balancer (GLB)

El Gateway Load Balancer (GLB) es un tipo de balanceador diseñado para manejar tráfico de red completo (nivel 3 del modelo OSI).
Esto significa que no trabaja con solicitudes web (HTTP) ni con conexiones TCP específicas, sino con paquetes IP completos — tal cual como viajan en Internet.

👉 En otras palabras:

El GLB no reparte usuarios entre servidores web, sino que reparte tráfico de red, normalmente hacia appliances virtuales (como firewalls, IDS, antivirus o proxies).

🧠 En palabras simples

Imagina que todo el tráfico que entra o sale de tu red (VPC) pasa primero por un “puerto de seguridad”,
y ese puerto decide por cuál firewall o filtro enviarlo antes de que llegue a tus instancias.

Eso es lo que hace el Gateway Load Balancer:

Se pone como puerta de entrada (gateway) del tráfico.

Lo distribuye entre varios dispositivos virtuales (firewalls, inspección, monitoreo, etc.).

Los combina en alta disponibilidad y sin interrupción.

## Grupos de autoescalado. 

Los recursos idealmente deben estar casi siempre por encima de las necesidades. 

¿Como conseguir estar en ese escalado que se creen más instancias o se reduzcan?

**Escalado In** Hacia adentro / Menos instnacias 

**Escalado Out** Hacia afuera / Más instancias. 

Puedo hacer un **grupo de auto escalado**.  Puedo configurar un minimo y un deseado de instancias de EC2 por ejemplo , aquí estoy gestionando el autoescalado.

Puedo hacerlo manualmente: (Mañana es black friday entonces le voy a aumentar las instancias porque se que lo necesite.)

Puedo hacerlo dinámicamente: (Le paso datos, basado en esos criterios que hagan que se creen o disminuyan instancias automaticamente. )