# Rol

Es una identidad IAM con permisos especificos tiene asignada una politica.

El Rol esta diseñado para que lo pueda asumir :

 - Una persona ,
 - Una aplicación (un SDK) ,
 - Un servicio (Ejm: A una maquina virtual que le damos un rol para que obtenga permisos )

Es decir, se le puede aplicar a cualquier entidad que se le requiera aplicar unos permisos determinados. Esto es temporal para realizar tareas. 

**Un rol proporciona credneciales temporales** Supongamos que un usuario tiene permisos para administrar una base de datos, pero puede obtener permisos superiores para modificar mas profundamente la base de datos, por medio de un rol que actua como administrador.

Un usuario tiene acceso a un **Bucked de S3** y además necesito que una instancia de EC2 pueda tener accesi a ese Bucked de S3. Es decir, la instancia entera, el servicio completo le puedo dar permiso de lectrua al Bucked de s3 , y el ususario quizas continua con sus permisos de lectura y escritura. Esto se lo asigno por medio de estos roles.

# **Politicas de IAM.** 
Los permisos se asignan por medio de la creación de una politica de IAM. 

De forma pretederminada todos los permisos estan en 0, todos denegados y vamos desbloqueandolo con el uso de la política

## **Tipos de políticas**

``Políticas basadas en la identidad.``

Referencia a las tres identidades: Usuario / Grupos / Rol

Tengo varias politicas. Asignadas a las identidades 

1. Un grupo por ejemplo tiene acceso a una varias politicas que le dan acceso a un recurso.

2. Si el usuario pertenece al grupo hereda las politicas. 

3. Si hay un Rol que tiene acceso a algunas politicas, todas las entidades ( Uusaurios / grupos / servicios) que se acojan a este rol, podran tener acceso a estas políticas.


``Politicas basadas en recrusos.``

Son los propios recursos los que tienen una política asociada. Por ejemplo hay una politica que dice que a este recurso solo se puede acceder en tipo lectura. 

Supongamos que tengo 2 politicas. 

1. Para un grupo: Que me dice tienes permisos de ``lectura y escritura`` para el recurso 1 (Ejm: **Bucked de S3**)

2. Para el mismos recurso: Tengo permisos de ``lectura unicamente`` para este recurso 1. El mismo Bucked de S3. 

Cuando el grupo intente acceder al recurso, las políticas aparentemente se contradicen. **``Pero en AWS la que prevalece es la más restrictiva.``** Por lo tanto se impone la politica del recurso, de solo lectura. 


## **Como se aplica la desición al momento de acceder a un recurso.** 

1. ¿El permiso está ``denegado`` de forma explicita? 

Si, Si hay una politica especifica que lo deniega: Resultado **Se deniega**

(En caso de que no exista. esta politica de denegación explicita.)

2. ¿El permiso está **permitido** de forma explicita.

Opcion 1. 

No, No hay una politica que lo permita de forma explicita: Resultado  **Se deniega**

Opcion 2. 

Si, Si hay una politica que lo permita de forma explicita: Resultado **Se permite** 

En conclusión **solo se permite el acceso / permiso** si hay **UNA POLITICA EXPLICITA QUE LO PERMITA**  y no exista ninguna **POLITICA QUE INFLUYA A LA MISMA ENTIDAD,  QUE LO DENIEGUE (es decir que sea mas restrictiva)**

Siempre se debe aplicar la politica de **privilegio mínimo**, la política de IAM debe conceder lo mínimo posible para hacer el trabajo, no al reves. Siempre se debe ir concediendo lo imprescindible, y si se deja de usar o es necesario, se deben reducir los privilegios. 

Desde el panel de IAM:

Podemos crear: 

- Usuarios / grupos y **politicas** para los mismos. Usando las predefinidas ó no predefinidas. 

Una política visualmente la podemos ver como un fichero JSON. 



Podemos además crear un Rol y vincularlo: 

- A un servicio 
- A una cuenta 
- A una identidad

Podemos crear un Rol , y luego asignarlo a una instancia de EC2.  Por ejemplo. Decir que la instancia de EC2 , puede tener acceso a una instancia de S3 y solo va tener acceso de lectura. 

Luego puedo entar a mi instancia de EC2 e ir a la parte de seguridad para asignarle el rol que hemos creado. 

