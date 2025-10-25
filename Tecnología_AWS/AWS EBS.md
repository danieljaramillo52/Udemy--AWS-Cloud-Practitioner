# EBS Elastic block storage. 

Almacenamiento NO COMPARTIDO.

🧱 Entonces… EBS no es compartido
El almacenamiento EBS (Elastic Block Store) NO es compartido en ese sentido.

- EBS funciona como un disco duro individual conectado a una sola máquina EC2.
Solo esa instancia puede leer y escribir directamente sobre ese volumen.

🔹 Si quieres que otra instancia use ese mismo EBS, tienes que:

“Desconectarlo” de la primera instancia.
“Conectarlo” a la otra (como desconectar un disco USB de un PC y ponerlo en otro).

- No puede estar montado en dos instancias al mismo tiempo (con excepciones muy específicas de configuración avanzada).

- Permite crear volumnes y asociarlos a una instancia de EC2 (Recordar al crear la instancia como nos ofrecian , elegir almacenamiento y la mayoria era del tipo EBS)

- **``Ofrece alacenamiento a nivel de bloques``**: Supongamos que:

- Edicion de un libro de varias gb 
- Edicion e libro de miles de paginas

Si el acceso es a **nivel de bloques** puedo solicitar los cambios, la actualización de unos **bloques** determinados , asi mas facil, (Comparablemente pensemos: supongamos que hacemos solo un cambio en un script, puedo vover a pasar todo el proyecto o puedo pasar solo el script)

Esto lo puedo hacer a nivel de bloques. Si por el contrario tengo almacenamiento a ``a nivel de objetos`` tendria que modificar **todo el objeto**, tendria que mandar el elemento completo , el fichero completo. El acceso a los datos puede ser muy frecuente y no puedo estar mandando una y otra y otra vez los cambios. con el objeto completo. 

Supón que tienes un archivo de texto de 1 GB.
Solo cambias una palabra → el sistema operativo escribe unos pocos bytes dentro de un bloque, y listo. El resto del archivo no se toca. **(Pero esto no lo hago yo manualmente es automatico**)


Los volumnenes sabemos se replican en varias zonas de disponibilidad para obtener disponibilidad de mis datos. 

**Por otro lado** puedo utilizar S3 para almacenar las correspondientes copias de seguridad, para el almacenamiento de objetos. 

- Claramente **se puede gestionar con elasticidad**, es decir definirlo con un tamaño e irlo aumentando o disminuyendo si se requiere. 

- Se puede **reservar e implementar en:** 

    1. SDD: Mas recomendada para la mayoria de situaciones. Particiones de sistemas para acceder mucho, baja latencia etc. 

    2. HDD (clasicos): A mucha cantidad de datos / big data almacenamiento de datos. 

``Costos:``

1. Todos los **volumnes** se cobran en función de la cantidad de espacio que se aprovisione por mes, es decir, la cantidad de espacio que reservo para utilizar.

2. Al hacer instantaneas en S3 (copias de seguridad), se cobra en función de los GB copiados al mes.

3. La transferencia de datos entrante es gratuita. Lo que yo este guardando no se cobra nada, pero al transferir datos ``entre regiones`` también se cobra, No se cobra entre zonas de la misma región, pero de una región a otra si. 


4. **IOPS : Input / Output per Second:** Los dispositivos tienen esto. Es la cantidad de intrucciones de entrada y salida por segundo, el amacenamiento se le pueden hacer muchas peticiones por segúndo , el dispositivo tendra esta caracteristica más o menos avanzada. Y los dispositivos tienen mas o menos capacidad y los puedo elegir para nuestra instnacia. 

