## Infraesturctura global de aws. 

Estructura general de AWS. (Existe infraestructura en todo el mundo.)

Se divide en regiones / Para asegurar disponibilidad, repetición. etc.

## Servicio AWS CloudFront. 
**``Red de distribución de contenidos. (CDN (Content Delivery Network).)``** 
Sistema de cacche  distribuidos a nivel mundial. 


Necesitamos tener algo llamado ubicaciones de borde / edge location / ubicaciones perifericas. A lo largo del mundo existen muchos puntos donde hay centros de datos. Esto se distribuye, por todo el mundo, las peticiones que hacen los usuarios se alamcenan en cache en estos centros de datos, más cercanos a la zona del usuario y cuando vuelvan a solicitar este contenido se utiliza esto ya guardadado para obtener una mejor latencia. 

Existen más de 225+ de estos puntos de borde. 

### **Niveles jerarquicos de distribución:**

1. #### **🔹 Edge Locations**

``Qué son:``
Son los puntos de presencia (PoPs) más cercanos al usuario final, ubicados en cientos de ciudades.

``Función:``
Entregan directamente el contenido al cliente (por ejemplo, una página web, video, imagen, etc.).
Si el contenido está en caché ahí, se devuelve inmediatamente sin necesidad de ir más arriba en la jerarquía.

``Beneficio:``
Baja latencia y respuesta rápida, porque están geográficamente cerca del usuario.

``📍 Ejemplo:``
Un usuario en Bogotá solicita una imagen de tu sitio: si hay una Edge Location en Bogotá o Lima, CloudFront la sirve desde allí directamente.

2. #### **🟣 Multiple Edge Locations**

``Qué significa:``
Indica que un objeto se entrega desde más de una Edge Location (por ejemplo, varias ciudades en la misma región), o que CloudFront usa varias ubicaciones de borde para balancear la carga y asegurar alta disponibilidad.

``Función práctica:``
Permite que múltiples puntos de borde mantengan el mismo contenido en caché, garantizando redundancia y distribución global eficiente.

``📍 Ejemplo:``
Si un video popular es solicitado desde varias regiones cercanas, CloudFront lo replica en varias Edge Locations simultáneamente.
`

3. #### **🟠 Regional Edge Caches (REC)**

Qué son:
Son niveles intermedios de caché entre las Edge Locations y el origen (S3, EC2, Load Balancer, etc.).

``Función:``
Si una Edge Location no tiene el contenido, antes de ir al origen, busca en el Regional Edge Cache.
Esto reduce los viajes costosos al origen y mejora la eficiencia de la red.

``Beneficio:``
✅ Menor carga en el origen
✅ Mayor probabilidad de "cache hit"
✅ Mejor rendimiento general para usuarios en toda la región

📍`` Ejemplo:``
Si las Edge Locations de Bogotá y Lima no tienen un archivo, el REC de São Paulo podría tenerlo, evitando una ida al S3 en Virginia.


🧠 Resumen jerárquico
Usuario → Edge Location → Regional Edge Cache → Origen (S3/EC2/etc.)


Cada nivel busca entregar el contenido lo más cerca posible del usuario, y solo si no está en caché, sube al siguiente nivel. Trata de buscarlo en niveles mas bajos (cercanos primero)`


## AWS Local Zone. 

CDN  Content delivery Network (**Más orientado a los contenidos**)

Este servicio por otro lado , está más orientado a la optimización de la distribución de servicios no tanto de contenidos, existen zonas disponibles para que haya mejor latencia en los servicios.

## AWS WAVELENGTH

Infraestructura que ofrece optimización para redes moviles ( Para aplicaciones moviles especificmanete). (Red 5g. ) 