# **Servicios adicionales de seguridad**

## AWS COGNITO 

Control de acceso para aplicaciones web y moviles.

Identifica a usuarios que quieren acceder, utilizando diferentes métodos. 

Seguridad, identidad y conformidad

**Se puede acceder a traves de terceros** (Cuenta auxiliar (GOOGLE / FACEBOOK / Amazon)) para gestionar una identidad en cuestion. 

**Amazon Cognito**

Identity and access management segura para aplicaciones

Con Amazon Cognito, puede agregar registro y inicio de sesión a sus aplicaciones. También puede obtener credenciales temporales de AWS para acceder a sus recursos en la nube

- Utilice Amazon Cognito como proveedor de identidad y agregue soporte para autenticación flexible, autenticación multifactor, contraseñas de un solo uso, dispositivos biométricos y claves de seguridad.

### **Adicional :** 

``Puede proveer credenciales temporales para el acceso a servicios de aws``


## **AWS Shield.**

Protege contra **``ataques de denegación de servicio.``**

👇

### 🧠 ¿Qué es un ataque de denegación de servicio (DoS)?

**``Un ataque de denegación de servicio (Denial of Service, DoS)``** es un tipo de ciberataque cuyo objetivo es interrumpir el funcionamiento normal de un servidor, aplicación o red, saturándola con un exceso de tráfico o consumiendo sus recursos (como CPU, memoria o ancho de banda).

Cuando esto sucede:

Los usuarios legítimos no pueden acceder al servicio (por ejemplo, un sitio web deja de cargar o se vuelve muy lento).

El atacante no busca robar datos directamente, sino causar indisponibilidad.

### 🚨 Variante más peligrosa: DDoS (Distributed Denial of Service)

En un DDoS, el ataque proviene de miles de dispositivos distribuidos en todo el mundo (una “botnet”), todos enviando solicitudes simultáneamente al mismo destino.
``Esto lo hace más difícil de detener, ya que el tráfico parece venir de muchas fuentes diferentes.``



## **AWS GuardDuty**

``Escanea permanentemente lo que pasa , Contenedores, bases de datosm usuarios, instancias, cargas de trabajo. Etc``

Busca **detectar potenciales amenazas de seguridad** de forma PROACTIVA. Es decir, establece una supervicios continua y avisar en tiempo real de posibles amenazas de seguridad. 


## **AWS Detective**

Análisis de log, registros del sistema, investigación de cosas que han pasado para sacar conclusiones con respeto a los eventos que ya sucedieron y/o tomar acciones para prevenir y detectar amenazas de seguridad. La diferencia con **AWS GuardDuty** se entiende en el sentido de que **AWS Detective** depende de información de log o registros de eventos que ya han pasado. Y no es una detección en vivo en tiempo real como **AWS GuardDuty**


## **AWS Inspector**

Trata de encontrar vulnerabilidades , por ejemplo en los servicios de **EC2** , por ejemplo ya sabemos que el software que metamos en una instnacia de ECS como lo configuremos es **nuestra responsabilidad** del usuario. Pero la idea es que este servicio nos indica, vulnerabilidades de ese software, de funciones lambda, buscar puertas traseras que representen riesgos de seguridad. Puertos que quiza quedan abiertos en nuestro software. Etc. 

Es un escaner de vulnerabilidades, es un apoyo a nuestra administación de nuestros sistemas.

## **AWS MACI**

Servicio de **``seguridad y privacidad de DATOS``**, especificamente de datos **almacenados en S3** revisión de que no hayan fugas de datos , control de acceso , que no exista una configuración inadecuada. Todo lo que ocurre con nuestros datos.


