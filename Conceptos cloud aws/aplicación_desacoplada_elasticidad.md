# Arquitectura de aplicaciones Monolitica vs Desacoplada. 

Tradicionalmente todo el código estaba de manera monolitica. 

Había modulos como maximo entre ellos se llamaban pero todo es un mismo elemento. No hay un desacople entre ellos. 

Tú aplicación es **monolítica modular**: tiene buena organización interna, pero el despliegue y la ejecución siguen siendo centralizados en un único bloque. Directamente desde el main. Referente a las aplicaciones de (XpertGroup -> (Propias) -> Para Comercial Nutresa). 

A veces todos los elementos del sistema: (De la aplicación tiene necesidades)

- Dle microprocesador (computo) / almacenamiento / base de datos / mi código. 

Todos los elementos pugnan por los recursos del sistema,

Al ser **Monolitica** no se pueden separar. y pues los recursos no se usan eficientemente. Si un componente consume demasiado, también va a generar cuellos de botella en el sistema que afecten los demas. Y se corre el riesgo de que si un falla los otros tambien.


## Aplicación enfocada en microservicios. 
- Para corregir el problema anterior, vamos a enfocar las aplicaciones en **Microservicios** esto permitirá desacoplar los componentes. Que los componentes sean capaz de separarse.  Los elementos trabajan en entornos diferentes. Cada entorno se puede adaptar para ser eficiente según las necesidades. Ejm: Un componente de bases de datos trabaja de manera eficiente, de forma independiente. Y el componente de un código en php optimizado también para esto. **Las funcionalidades están desacopladas por el entrono** pero se comunican continuamente. 


# **¿Qué es la elasticidad?**

Recoerdar. 

Supongamos una instancia de una VM con. 2 CPU / 4 GB de ram.

Escalado horizontal: Aumentar los elementos existentes. Ejmplo:

**Una instancia** : 2 CPU / 4 GB de ram.
**Otra instancia** : 2 CPU / 4 GB de ram.
**Tercera instancia** : 2 CPU / 4 GB de ram.


Escalado vertical: Aumentar la potencia de la instancia ya existente. (Ejm: Maquina virtual: 4 CPU / 8 GB de ram)

Esto está relacionado con las aplicaciones de **Microservicios** y las **monoliticas**. Una aplicación monolitica que solo tiene una comunicación solo se le puede hacer un escalado vertical. Aumentar los recursos de una sola instancia. 

Por otro lado. en las de microservicios puedo utilizar mejor el escalado horizontal y justo donde lo necesito. 


## Conceptos. 

### scale out / scale int. 

Supongamos que tengo un periodo de necesidad y tengo unas máquinas que se comunican: 

1 --- 2 --- 3

Como tengo un periodo de mucho tráfifo entoces realizo un proceso de **```Scale out```** **aumentando** más maquinas.


1 --- 2 --- 3 --- 4 --- 5

Pasado ese periodo de alta demanda puedo restablecer la potencia inicial. **```Scale out```** **reducir** 

1 --- 2 --- 3 


## Procesamiento en paralelo. 

El proceso **Monolitico** puedes intentar "partirlo" intentar procesarlo por partes. Solo hay una entidad procesando. **El paso 2 no se puede realizar sin haber completado el paso 1.** no es tan efectivo ni importante el pensamiento en paralelo. 

Por otra parte. 

**La aquitectura en microservicios**
Yo puedo crear muchas instancias para procesar en paralelo, al mismo tiempo. Esto es la elasticidad. La nube permite esto más facil. Todo mi software debe poder trabajar varios todos a la vez comunicandose. 

