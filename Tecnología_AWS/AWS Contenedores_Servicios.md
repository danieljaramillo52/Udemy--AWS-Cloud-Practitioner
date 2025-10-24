# Servicios para contenedores en AWS. 

## **AWS Elastic Container Service** 

Servicio de administración  de contenedores (Altamente escalable)

Funcionalizades:

- Optimiza la ejecución de contenedores de docker. (Puede manejarse por medio de un cluster). 

- Mantiene y escala la flota de nodos que ejecutan los  contendores. 

- Elimina la comoplejidad de poner en marcha la infraestructura.  Elimina la complejidad de la infraestructura física. Un servicio mantenido con aws , hace que tenga mucha compatibilidad con todo los servicios de aws. 


### 🧩 1. ¿Qué es un cluster?

Un ``cluster es un conjunto de máquinas (físicas o virtuales) que trabajan juntas como si fueran un solo sistema.``

Estas máquinas pueden estar en distintos servidores o incluso en diferentes zonas geográficas, ``pero el orquestador (como Kubernetes o ECS)** las trata como una unidad lógica.``

Cada **``máquina``** dentro del cluster se llama **``nodo``**.

Un **``nodo puede ejecutar varios contenedores``** (cada uno con una aplicación o microservicio).

Uno o varios nodos se designan como nodos maestros (control plane), los cuales se encargan de asignar trabajo, monitorear, escalar y reiniciar los contenedores.


Cluster Docker
├── Nodo 1 → ejecuta contenedor A, B
├── Nodo 2 → ejecuta contenedor C
└── Nodo 3 → ejecuta contenedor D, E, F

un cluster es el “grupo organizado” de servidores donde se ejecutan tus contenedores.

### 2. Escalar flota de nodos. 
Si tu aplicación recibe más tráfico o trabajo, el orquestador añade más nodos (máquinas) o más contenedores dentro de los nodos existentes para mantener el rendimiento.

Si la carga disminuye, el orquestador reduce el número de nodos o contenedores para ahorrar costos

Este servicio se puede integrar facilmente con el servicio de **AWS EC2**


### Elección para la administración. 

Podemos administrar nosotros mismos el **cluster** puedo administrarlo con instancias  de EC2. 

Pero si lo que me interesa es no administrar el manejador del contenedor el cluster, Si yo solo quiero manejar los contenedores y deswpreocpuarme de los nodos cluster , so etc. 

Podemos utilizar **AWS Fargate** para que funcione serverless. (Solo administro los contenedores)

-----
Fundamental: 

## 🐳 AWS Elastic Container Service (ECS)

Es un servicio de orquestación de contenedores.
Permite definir, ejecutar y administrar contenedores Docker en AWS.
👉 Es el “cerebro” que organiza cómo, dónde y cuántos contenedores corren.

#### Y Utilizo EC2 para administrar.

Cluster Docker
├── Nodo 1 → ejecuta contenedor A, B
├── Nodo 2 → ejecuta contenedor C
└── Nodo 3 → ejecuta contenedor D, E, F

### ⚙️ AWS Fargate

Es un motor de ejecución sin servidor para ECS (y también para EKS).
Permite ejecutar contenedores sin gestionar servidores o instancias EC2.
👉 Tú defines los recursos (CPU, RAM) y Fargate se encarga del resto.

Me despreocupo de SO/Maquina/Docker. **Solo me preocupo del propio contenedor.**
----


### ECR : Elastic Container Registry. 

Podemos guardar nuestras propias imagenes personalizadas. 

- Compatible con docker , Integración , administración e implementación de imagenes de contenedores de docker. Compatible con ECS (Elastic container service / Compatibilidad con terceros. )

### EKS : Elastic Kubernetes Services 

Administración de cluster  de instancias de EC2 y administrar contendores que estan organizados por Kubernetes en esas instnacias. 
