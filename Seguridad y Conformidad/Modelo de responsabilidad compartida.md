# Responsabilidad customer / aws. 

El **usuario/cliente/customer** es responsable de la seguridad **en la nube** y **aws** es responsable de la seguridad **de la nube**.

Diferencia ? Depende del serivicio pero en general: 

**AWS**: Es responsable del harware y de la infraestructura global. Bien comunicada latencia correcta / trafico redundante. Esta infraestructura está dividida. 

**ASW** : Del computo almacenamiento / de las bases de datos (A nivel de infraestructura , como de servicio si lo contratamos como SaaS) / de su propia red de infraestructura. El software que hace que toda la infraestructura de nube funcione. 

**customer / cliente** : Datos propios del usuario, aws pone la nube pero tu eres responsable de los datos, lo que tu tulizas es tu responsabilidas, la aplicación que uses en la nube (que has programado) / identidade claves de acceso. (como se accede a la nube). 

**customer / cliente** : Si has contratado una instancia tipo plataforma tu eres responsable de que esa plataforma funcione. 

Ejemplo: Una instancia de una maquina virtual. Donde yo tengo el espacio y estoy encargado de instalar todo, SO. Conectar instnacias , redes configuración , encriptación en datos del cliente si viajan cifrados. Podemos habalar tambien del servidor la configuración del mismo / control de red identidad por ejemplo.


En resumen. **NOSOTROS SOMOS RESPONSABLES DE LO QUE OCURRE EN LA NUBE** Y **AWS de garantizar que funcione esa nube**


## Ejemplo de responsabilidad compartida con una implementación. 

Tomemos la **NUBE DE AWS**

1. Tenemos contratados unos servicios: (Instancia de Amazon EC2 y una Instancia separada de Oracle) trabajando ambas dentro de: Virtual Private Cloud.

2. Además tenemos un servicio de **Almacenamiento S3**

### **Preguntas** 
¿Quien es responsable de las actualizaciones y parches de una instancia EC2? 

Una instancia EC2 es una IaaS: Solo hemos contratado la infraestructura, por lo tanto las actualizaciones y parches del SOFTWARE que vamos a trabajar ahí es responsabilidad del **cliente**

### ¿Seguridad física del centro de Datos?: 

AWS de cajon, es responsable de garantizar la integridad física y seguridad del centro de datos. (Todos los servicios contratados están sobre un centro de datos. **De la nube**)

### ¿Infraestructura de virtualización? 

**Definición de virtualización:** La virtualización es una tecnología que se puede usar para crear representaciones virtuales de servidores, almacenamiento, redes y otras máquinas físicas. El software virtual imita las funciones del hardware físico para ejecutar varias máquinas virtuales a la vez en una única máquina física.

En resumen es un **```entorno virtual```** sobre **```hardware real```** , que todas esa virtualizaciones se creen y funcionen correctamente.  De AWS.

Nosotros no estamos creando esa infraestructura ni gestor de contenedores ni nada. **Estamos contratando** , AWS se encarga de virtualizar como considere oportuno. 


### ¿Configuración de grupos de seguridad de EC2? 

Esta pregunta hace referencia a COMO VAMOS A USAR , COMO VAMOS A ACCEDER al servicio EC2, por lo tanto, es responsabilidad del cliente. 

### ¿Configuración de las aplicaciones que se ejecutan en una instnaica de EC2? 
aws **nos proporcionó la instnacia**, las aplicaciones que utilicemos en la instancia y como queremos configurarlas son responsabilidad del **cliente**. La instancia ya sdabemos es IaaS. Por lo que lo demas dentro de ella ya será nuestra responsabilidad

### ¿Actualizaciones o parches de oracle, si la instancia se ejecuta como una instnacia de Amazon RDS? 
