# Cifrado de Datos: 

Datos almacenados y en transito. 

Los datos estan almacenados en algun punto especifico y debemos acceder a esos datos desde el cliente desde nuestra ubicación. 

## Cifrado de Datos: 

Aplicar técnicas de cifrado y encriptación donde tenemos claves necesarias para acceder a esos datos. (Datos en disco que no se están moviendo de un lugar a otro. )

## Transito de datos

Los datos estan moviendose el sistema no está cerrado. Tambien debemos cifrar los datos que están en transito. Si son interceptados, no deberian ser de facil acceso no deberia haber posibilidad. 

### Condiciones del cifrado de datos. 

Servicio empleado KMS (KEY MANAGEMET SERVVICE) Sirve para gestionar las claves de cifrado. compatible con todos los servicios. ``Debemos activar para asegurar que el cifrado esté activo. Activar todos los métodos de seguiridad (cifrado en almacenamiento y en transito)``

Método de (SSL) : Capa de cifrado de seguridad técnologia (En transito)
Método de (TLL) : Servicio más moderno y actualizado para el cifrado de datos. 

### Resumen: 
- Usuario es responsable de activar el cifrado de sus datos. 
- En transito tenemos TLS para comunicarse / la mayoria de los servicios se comunican de forma cifrada. 
- KMS es el servicio de gestón de claves de cifrado
