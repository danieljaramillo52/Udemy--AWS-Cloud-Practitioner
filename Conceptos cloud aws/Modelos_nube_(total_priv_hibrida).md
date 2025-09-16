# Modelos de nube. total (publica) / privada / hibrida. 

**Nube privada:** Infraestructura / recursos utilizados para que todo funcione es de acceso privado. Solo los de la empresa ningun agente externo puede acceder a los servicios ni a los servidores. 

**Nube publica:** Utiliza servicios de nube, NO SIGNIFICA QUE TODOS PUEDEN GASTAR DE MIS RECURSOS,  pero los recursos de esa nube si los puede subcontratar cualquier persona, estan disponibles a nivel publico para cualquiera que quiera contratarlos. AWS: pone a disponibilidad sus servicios dentro de la nube.

**Nube hibrida:** Una parte con recursos totalmente privadas y otra parte con recursos públicos ambos en la nube. Generalmente por cuestiones legislativas. 

Supongamos que tenemos una universidad: 

En la **Nube privada:** con los **recursos privados** gestiono información de alumnos / protección de datos /confiadencialidad de procedimientos dentro del manejo de la institución en mis propios servidores. Por otra parte tengo una **Nube publica:** donde despliego por ejemplo la pagina de acceso publica para la comunidad a la que quiero distribuir los datos. Las dos partes privada y publica se conectan. 


# Infraestructura tolerante a errores. 

## Conceptos importantes. 

```Tolerancia a fallos y alta disponibilidad```

Se tiene una tasa altisima en cuanto a la disponibilidad del servicio. es decir una **tasa admisible** es 99.9 , pero una tasa de  alta disponibilidad, y una tasa de disponibilidad mayor. **99.999**

Puede fallar: 
1. El hardware 
2. Los datos (suseptible a un ataque por ejemplo).

Todo se soluciona duplicando servicios: Recurro a sistemas duplicados.
Ejemplo: RAID. Se enfoca en trabajar con varios discos que **replican los datos.** esta replicación es indispensable por si hay una falla de un disco de hardware que está en un disco, si este falla, entonces el otor disco entra en funcionamiento de inmediato.

**Esto es diferente** a una **copia de seguridad de los datos**. Necesaria para contrarrestar un tipo de ataque que es un Ramsoftware que corrompa y/o inabilite los datos.  Esto ya es una copia a nivel de software. 

Además respaldos físicos por fallas electricas/estructurales/físicas. 

**De esto tambien se encarga el proveedor**. Pero podemos manipularlo nosotros por ejemplo con: **Un balanceador de cargas** permite re-dirigir de una zona u otra, por si las instancias de una zona fallan. Permite que la segunda zona asuma las funciones por ejemplo. Hay una sincronización entre ambas.