# AWS EC2 Optimizar costes 

Tipos de instancias:

## 1. Instancia del ejemplo (Instancia bajo demanda). 

Se nos asigna pero no sabemos , en cual servidor está , no sabemos en que lugar de la infraestructura dentro de la región 

- Pago por hora 
- Flexible para creación y cancelación (Crecer en determinado momento / Cancelar si no hace falta)
- Apto para el plan gratuito. 

## 2. Instancias dedidcadas. 

Con la anterior no tenemos ningun control sobre ella (donde está donde se ejecuta.) 

La instancia se ejecuta en una **VPC (Virtual Private Cloud)** que tiene un hardware dedicado a un solo cliente. Puede ser necesario por:

- Cuestiones legislativas legales
- Cuestiones de seguridad 

(Yo controlo todo lo que pasa con todas las instancias que pasa en ese **hardware** PEROOOOO, ``Tú no ves ni controlas el host físico.``

``AWS decide en qué host colocar cada instancia dedicada.``

``Se cobran los mismos precios base de instancia EC2, más un pequeño recargo por aislamiento. ``
)
- Precio mas elevado, **al exigir un hardware para el uso propio de una determinada cantidad de instancias**

## 3. Instancias (Host dedidcados). 

Servidor FÍSICO con capacidad de instancias EC2 totalmente dedicado a su uso. 

2. Hosts dedicados (Dedicated Hosts)

Qué son: servidores físicos completos (no compartidos) que se te asignan directamente.

**Tú puedes:**

Ver el hardware físico.

- Controlar qué instancias se colocan en él.

- Reutilizar licencias de software por socket o CPU (Windows, Oracle, etc.).
(Algunos host privados se alquilan pensando especficiamente en las licencias de ese software.)


Tener visibilidad total de la utilización del host.

🔹 Aquí ya no hablamos de “una VPC virtualmente aislada”, sino de un servidor físico real reservado para ti dentro de AWS.

``Costo: mucho más alto, ya que pagas por todo el host físico, no por instancias individuales.``

--- 

| Característica | Instancia dedicada | Host dedicado |
|----------------|--------------------|----------------|
| **Nivel de aislamiento** | Hardware dedicado solo para tu cuenta | Hardware físico asignado 100% a ti |
| **Control sobre el host** | ❌ No | ✅ Sí (ves el host, su capacidad, ocupación, etc.) |
| **Gestión de instancias** | Automática por AWS | Manual: tú eliges qué instancias van en el host |
| **Ideal para** | Cumplir requisitos de aislamiento y seguridad | Cumplir licenciamiento BYOL (Bring Your Own License) o control total |
| **Precio** | Más alto que instancias normales | Mucho más alto (pagas el host entero) |


4. ## Instancias reservadas. 

Puedo reservar una capacidad de computo, si yo tengo la plena seguridad de que necesito que se mantenga una demanda medianmente estable y constante a traves del tiempo.  En ese caso puedo tener una ``Instancia reservada``

Caracteristicas

- Me comprometo con un acuerdo de pago.  ( 1 - 3 años ) / No se cancela
- Vinculadas a que sabemos que si o si o si las vamos a utilizar. 


5. ## Instancias de spot. 

Instancias **Muy económicas** se ejecutan con recursos "libres" que **no estan siendo solicitados**  y siempre que esten disponibles las mismas instancias y recursos.

Ocupa solo lo que no se ha solicitado de una forma más cara. **El precio que cobra la instancia de spot por los recursos usados puede ser muy mínimo. hasta un 90% menos**.

Problematica principal: Las demas instancias si solicitan recursos y se empite un costo mayor a estas, automaticamente los recursos del spot se desaprovisionan ya que tenemos la peor preferencia. 

Recibimos una notificación de dos minutos, y se detiene automaticamente con una **detención** o **hibernación**, Se pueden usar para procesos que no requieran mantenibilidad online 100%. **``Que la aplicación se pueda interrumpir sin causar problemas y que tenga flexibilidad sobre el cuando vamos a procesar estas instancias``**


---

# AWS EC2 OPtimizar costes parte 2. 

Cuando tenemos claro mi tipop de instancia a lanzar podemos: 

1.**#### Adaptación del tamaño** Intentar optimizar los recursos. , aprovisionar solo lo que de verdad necesito. ¿Como? **``Usando las meticas de AWS CloudWatch``** para hacer el análisis real de lo que estamos utilizando y determinar que necesitamos realmente segùn su uso. 

2. #### Aumento de la elasticidad. 

Tratar de que las instnacias se puedan detener o hibernar cuando no se están utilziando **automatizar el escalado de una instancia** para satisfacer necesitdades en función de su uso / Vamos menguando o aumentando la infraestructura según necesitamos. 

3. #### Modelo de precios optimo. 

Aprovechar el modelo de costos según el uso que vamos a dar a la instancia. 

Por ejemplo puedo combinar modelos de instancia. 

1. Reservar una instancia: con una capacidad determinada usual para mi tienda online.

2. Utilizar además una instancia bajo demanda para un momento puntual que mi tienda tiene epoca especial de ventas. 

Tambien puede existir la pregunta **¿Es necesaria una instancia de EC2?** o existe un recurso más economico Ejm: **AWS LAMBDA** ejecuta funciones sin necesidad de tener una maquina virtual reservada... Si existe un servicio que pueda cubir la misma funcionalidad de otro al 100% y mas barato, esa debe ser la elección. 

#### Optimizar el almacenamiento. 

El almacenmiento consume dinero depende del tamaño / el tipo / la calidad, si adaptamos el tamaño de los volumnes de almacenamiento cuando podemos ver si nos sobra. Tambien el tipo de disco ssd ? puede ser disco tradicional ?, cambiar los tipos EBS etc. 

## Recordar: 

## Nota EBS: 
Amazon EBS es un servicio de almacenamiento en bloques de AWS.
Proporciona volúmenes persistentes que se adjuntan a instancias EC2 (como si fueran discos duros virtuales).

📦 En otras palabras:
EBS = “disco duro en la nube” que puedes conectar o desconectar de tus instancias EC2.


