# AWS EC2 (Elastic Computer Cloud) 

## **Función principal:**
EC2 = Elastic Compute Cloud
``Proporciona máquinas virtuales (instancias) donde tú administras todo el sistema operativo.`` 

La palabra ``Elastic`` en AWS hace referencia a la capacidad de ``aumentar o reducir recursos según demanda.``

Desde EC2 puedes ejecutar prácticamente cualquier tipo de software, con control total sobre el sistema operativo, el almacenamiento y la red.

🔧 Características principales

**Variedad de instancias:**
Ofrece más de 600 tipos de instancias optimizadas para distintos casos de uso: cómputo, memoria, GPU, almacenamiento, red, HPC, etc.

**Personalización total:**
Puedes aprovisionar la instancia seleccionando el tipo de procesador (Intel, AMD, Graviton, GPU), la memoria, el almacenamiento (EBS, SSD, etc.), la red, y el sistema operativo de tu preferencia (Linux, Windows, macOS, etc.).

**Escalabilidad elástica:**
EC2 te permite ajustar dinámicamente la capacidad de cómputo según la carga de trabajo, aumentando o reduciendo instancias en segundos mediante Auto Scaling o Elastic Load Balancing.

**Integración con otros servicios de AWS:**
Se integra fácilmente con S3, RDS, CloudWatch, VPC, IAM y más, formando la base para arquitecturas modernas (microservicios, big data, IA, etc.).

**Modelos de costo flexibles:**
Puedes pagar solo por el uso real (On-Demand), reservar capacidad a largo plazo (Reserved Instances) o aprovechar precios reducidos (Spot Instances).


### **Casos de uso**

1. Infraestructura para ejecución de aplicaciones nativas (aws) y no nativas en la nube. Con todos los productos que ofrece.

2.  Desarollo para plataformas Aple. 

3. Entrenamiento e implementación de aplicaciones de machine learnig

4. Perfecto para aplicaciones **HPC significa High Performance Computing (Computación de Alto Rendimiento).**

Cuando AWS (u otro proveedor cloud) dice que una infraestructura o servicio puede escalar para aplicaciones HPC, se refiere a que puede crecer o adaptarse para soportar cargas de trabajo científicas, técnicas o de ingeniería extremadamente exigentes.


## **Consideraciones**

ECS es similar es como una maquina virtual que nos lanza AWS ,para configurarla como nosotros queramos.

¿Que debemos hacer? 

1. **Escoger una AMI** (Imagen del sistema operativo que vamos a meter en la instancia de EC2 , ¿Que quiero instalar dentro de mi instancia? ( Ubuntu / linux de aws / Windows ))

2. **Tipo de instancia** Con que recursos vamos a aprovisionar , cantidad de cpu , gpu tipo de procesador etc. 

3. **Configuración de Red** Comunicación de la instancia ( Red privada para instancia red publica)

4. **Permisos** Rol de la instancia y politica que se le agrega

5. **Datos de usuario** Lo que vamos a meter, revisión datos de usuario con un sripting etc. 

6. **Opciones de almacenamiento** Método de almacenamiento de información 

7. **Etiquetas** (Nombre descripción - Etiquetas accesorias para administrar mejor mis recursos)

8. **Grupos de seguridad** (Tipo de comunicación que se establece, tipo de acceso que tiene la instnacia al uso de la red, que puertos por ejejmplo tiene acceso la instancia)

9. **Claves de seguridad** Publica y privada para conectarme y administrar mi instancia de EC2. 

