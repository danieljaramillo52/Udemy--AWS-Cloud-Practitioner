## AWS EC2 estado de la instancia e ip publica. 

La instancia queda en estado "Activo / Ejecución" debemos poder detenerla. 

### **Ip publica de la instancia**
Para acceder a una instancia que está en ejecución, esta contiene una ip publica y por medio de ella podemos acceder a la instancia (Dirección abierta). 

Podemos tener una instancia en estado: Detenerla - Ejecutarla - Reiniciarla (Hay que cargar todo nuevamente) - Terminar ( Desaparecer la instancia. )

Al detener una instancia perdemos la IP publica / No la ip privada. 

``La IP publica desaparece. Ya no la tenemos, pero si vamos a iniciar nuevamente se reasigna una ip publica.`` Podemos conservar esa dirección **IP Publica**  si asignamos una dirección **ip elastica.**

Barra lateral de **``EC2>Red y Seguridad>Dirrecciones IP Elasticas>Asignar Dirección ip elestica>Asignar``**

Luego de estar creada podemos seleccionarla y damos al boton **Acciones** asociar la dirección ip elastica y ahora puedo asignarle la instancia.  ``Así si puedo convervar esa dirección ip publica  sin importar si detengo la instnacia. ``


### 📦 Límites de Elastic IPs

Sí, las Elastic IPs son limitadas por diseño.

Por defecto:

Cada cuenta tiene un límite de 5 Elastic IPs por región (no global).

Si intentas crear más, AWS te mostrará un error y te pedirá solicitar un aumento del límite a través del Service Quotas o el Support Center.

👉 Ejemplo: puedes tener 5 IPs en us-east-1 (N. Virginia) y otras 5 en us-east-2 (Ohio), sin que interfieran entre sí.

### 💰 Costos asociados

El uso de Elastic IPs tiene una regla importante:

| Situación | Costo |
|------------|--------|
| La Elastic IP está **asociada a una instancia en ejecución** | ✅ Gratis (1 por instancia) |
| La Elastic IP está **reservada pero sin asociar** | ⚠️ $0.005 USD por hora (~$3.60/mes) |
| **Más de 1 EIP asociada a la misma instancia** | ⚠️ También se cobra |


``Esto incentiva a liberar las IPs no usadas para no acumular cargos innecesarios.``

### **Adicionalmente:** 

Si hay una **ip-elastica publica** asociada a una instancia **deteneida** te va a cobrar. Entonces hay que tenerlo en cuenta. Y si hay una ip elastica sin necesidad (sin asociar tambien cobra ojo)