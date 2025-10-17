# IAM 
Gestor de identidades y de acceso. 

**Servicio fundamental que administra el acceso a los recursos de aws**

Supervisa y controla quien y como se accede a los servicicos. 

1. A que recursos se puede tener acceso
2. Quien puede tener acceso al recurso 
3. Que se puede hacer con el recurso
4. Como se puede obtener acceso ( Medio: Ejm : Como interactuo con el sistema ejm , por la consola el panel , comandos por un cliente de terminal etc. ) Permisos (leer / escribir)


# Fundamentales: 

### **Usuario IAM** : Persona que se puede autenticar con una cuenta de AWS.

Consideraciones: 

1. Por autenticar con una cuenta de AWS **no signifca** que todos los usuarios tienen todos los permisos: Ejemplo: El administrador de bases de datos solo tiene acceso a los serviccios de DB

2. Todos los usuarios no son **Personas**  en vivo y en directo accediendo, **un programa** puede acceder mediante un  skd (Una aplicación para el desarollo ) puede acceder y realizar algunas tareas y se cominica con el entorno


### **Grupos IAM** : Agrupamiento de usuarios bajo caracteristicas similares
varios usuarios ejem: 3 ingeneiros de datos tienen exactamente los mismos permisos, entonces puedo definir un grupo , donde incluyo usarios individuales y se aplican las reglas de este grupo. 


# Consideraciones grupos de usuarios IAM

1. Un usuario puede pertenecer a uno o varios grupos. Depende de las politicas

2. No hay ningun grupo predeterminado / debemos crear por su cuenta. 

3. No pueden haber grupos anidados no hay Jerarquia de un grupo a otro. No hay grupos uno dentro de otro.

4. Puedes poner muchos usuarios en muchos grupos **pero NO** un grupo dentro de otro tratando se que hereden los permisos Es mas un diagrama de ven en el universo de politicas pero no hay contención entre grupos. 


### **Politica de IAM** : Documento que define los permisos de usuarios y grupos sobre recursos y servicicos.

Estas politicas estan definidas quien los define , donde están a que recursos , por defecto al crear un usuario o un grupo por defecto tiene nivel de acceso 0 (No puede hacer nada. ) Y podemos ir creandola o predefinirlas que se puede hacer y a que nivel.

### **ROL DE IAM** : Mecanismo para conceder permisos ``temporales`` a solicitudes de servicios. Se puede conceder a cualquier entidad, usuario o servicio de aws.

Los servicios también pueden tener **Límitaciones** se les puede controlar de cierta forma, pueden necesitar permisos. Una maquina virtual solo tiene permisos de escriturá sobre un bucked de s3. Se le aplica ``Algo llamado permiso temporal`` que ejecuta algo. 

Ejemplo de Rol temporal en otros campos:

Por ejemplo en linux: Yo no soy un usuario administrador , pero al utilizar el comando ``sudo`` estoy logrando un permiso ``temporal`` de administrador  tengo un rol temporal de administrador. Estos roles obedecen a la **Politica de IAM** que le dan estos roles también.
