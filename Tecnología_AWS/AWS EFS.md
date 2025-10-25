# AWS EFS

Se orienta mas a un **almacenaiento compartido**. 

- Si varias instancias o contenedores necesitan compartir información este es el mejor tipo de almacenamiento. 

⚙️ Primero: qué significa “almacenamiento compartido”
``Cuando AWS dice que EFS (Elastic File System) es “almacenamiento compartido”, significa literalmente que:``

``Varias instancias EC2 o contenedores pueden acceder al mismo sistema de archivos (EFS) al mismo tiempo, leerlo y escribir en él como si fuera una carpeta compartida en red.``

- Compatible con linux NFS (Networt file system). 

- Esacala de manera ascendente o descendente a medida que se agregan o eliminan archivos. Solo requiere pago por lo que se utiliza. 

- Compatible con todas las AMI (Imagenes que vamos a instalar en todas nuestras intancias), de Linux para AWS EC2. La AMI será altamente compatible. 

