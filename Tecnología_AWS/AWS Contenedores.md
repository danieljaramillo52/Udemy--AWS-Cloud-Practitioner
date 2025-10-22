# **AWS Introducción al uso de contenedores**

Introducción al uso de los contenedores.

### 🧩 Definición general

Un contenedor es una unidad ligera y portátil de software que empaqueta una aplicación junto con todo su entorno necesario (dependencias, librerías, configuración y sistema base) para que pueda ejecutarse de forma consistente en cualquier entorno.

💡 En otras palabras:
Un contenedor garantiza que tu aplicación funcione igual sin importar dónde se ejecute — en tu laptop, en un servidor o en la nube.

### 🐳 Docker y los contenedores

Docker es la plataforma más popular para crear, ejecutar y gestionar contenedores.
Utiliza una imagen base (por ejemplo, una imagen de Python o Ubuntu) sobre la cual tú defines:

Tu código fuente, Dependencias, Variables de entorno, Comandos de ejecución.

De esa imagen se genera un contenedor, que es una instancia en ejecución de dicha imagen.

--- 

Secciones fundamentales. 

Contenedores: 

1. **Elastic Container Registry** : Permite guardar imagenes de los contenedores / Relacionado con docker, gestor de contenedores mas exitoso. 

2. **Elastic Container Service** : Lanzar contenedores y gestionarlos (orquestarlo)

3. ** Elastic kubernetes Service: **Orquestador de contenedores** :  Orquestarlo pero mas combatible con el tema de Kubernetes. 

--- 

# **Introducción a los contenedores (Docker)** 

Como podemos administrar nuestra infraestructura. 

**OPCION 1:**

Primero existian maquinas virtuales:  Se dividen los recursos del ordenador, mediando un **hipervisor** que divide los recursos de un hardware fisico de mi equipo, el hipervisor hace esas gestiones (Virtualizo parte del harware -> Lo arranco de manera aislada. ) **Ejm: de hipervisor : Virtual Box.** Y asi tengo un sistema aislado que usa parte de los recursos de mi hardware para trabajar. 

En cada maquina virtual ... **tengo diferentes SO**, pero entonces para cada entorno tengo que instalar un entorno , tengo que intalar un SO , y si lo que quiero solo es modificar una parte muy peuqeña por ejemplo una parte de una libreria. Me cuesta partir y separar el hardware. 

**OPCION 2:**
Tenemos un único SO ( Un unico Host operative system ) el **único sistema operativo** que se ejecuta sobre el hardware principal de mi equipo. 

**Docker** va tratar de aprovechar este entorno global el host, **y va a funcionar similar a mi entorno embebido**, Si yo quiero probar si mi wb funciona en php 5 , php 6 y php 7, entonces en cada contendor de docker solo tengo que instalar cosas más especificas y pequeñas. Creo mi imagen con lo que necesito y el verdadero diferenciador. 

--- 

La filosofia de un contenedor es:

1. Tengo mi SO que utiliza todos los recursos que puede / necesita de mi hardware. 

2. Tnego una imagen, tengo un fichero con un SO, por ejemplo Ubuntu. En el momento que ejecuto Docker run, el contenedor empieza a consumir recursos del sistema operativo, y puedo ejecutar instancias de la misma imagen y cada una será un contenedor que se ejecuta con los recursos del sistema. 

Todos utilizan recursos del SO. Yo puedo me puedo basar en todos los contenedores que yo quiera. 

