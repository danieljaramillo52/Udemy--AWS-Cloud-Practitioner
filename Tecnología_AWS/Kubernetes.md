# **Kubernetes**

Orquestador contenedores : Como tener muchisimos contenedores trabajando simultaneamente no (10 o 20) sino muchos cientos o miles. 

Queremos aislar funcionalidades: -> Contendores. Tenemos unidades aisladas del resto y cada una consume los recursos que cada una necesita instalando dependencias que cada una necesita. Etc. 

**Primero antiguedad:** 

1. ![alt text](image-9.png) En una misma unidad se manejaba todo a la vez todas la funcionalidades simultaneas y quiza no de la mejor manera. 

**Con contendores**

![alt text](image-10.png)  Tenemos cada instrumento manejado de manera independiente al otro, sin dependencia de lo que pase. Individualmente cada músico puede cotar su instrumento perfectamente. Cada contenedor indiviualmente funciona sin dependencias de los demás. 

Sin embargo... Si todos los musicos (Contenedores empiezan a tocar todos los intrumentos a la vez.) sería un descontrol , **se requiere alguien que las gestione , que las administre y que sepa que está haciendo cada una**

**``Kubernetes es el director de orquesta / Orquestador de contenedores``**

Kubernetes lanza cada contenedor cuando necesita - lanza todos cuando los necesita.

### Funcionalidades extra  (K8S == KUBERNETES)

1. Podemos gestionar todos los contenedores desde nuestro pc y los contenedores están alhojados en nuestro provedor de cloud. Y desde aquí controlarlos.

2. Es muy escalable: **Escalable vertical y Horizontalmente**, Puedo darle mas recursos a un contendor (vertical), o crear mas contenedores si lo necesito (Horizontal)

3. Reparación : Quizas necesito mas de una instancia de un contenedor , por si depronto uno de los dos se cae, el otro permanece funcionando mientras el kubermetes trata de levandarlo lo reinicia

4. Planificación : Reparte cargas de trabajo / planifica los recursos cuando quier oque se modifique el cluster (cantidad de elementos trbajando juntos), el va modificando los recursos. 

5. Peticiones: **El gestiona las peticiones web/rest** como una unica unidad al cluster. El recoge la petición lo envia donde corresponda a los contendores , balancea la carga y emite respuesta.

6. Despliegue: **Despiega cambios en todo el cluster** / Permite hacer un rollback es decir, si el despliegue falla puede volver a un estado anterior según la necesidad. 

![alt text](image-11.png)