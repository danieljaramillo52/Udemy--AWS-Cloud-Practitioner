 # Monitoreo en aws Cloud WATCH. 

## Monitorea valores de los servicios y recursos hardware.
Recopila datos operatvios y de monitoreo. (vigilante por excelencia de los servicios de aws ) , lugar central / unificado de lo que pasa con los servicios a modo de panel de control. Maneja control de logs registros, permite configurar todo tipo de metricas y eventos, y además, permite crear alarmas / permite escalado automatico / configurado etc . Configurar validaciones de facturación etc.


#  Monitoreo de AWS: CloudTrail. 

Monitorea acciones dentro de la cuenta.  Monitoriza en la actividad de la cuenta, quien está haciendo que, cuando y que recursos está usando. 

Monitoriza desde cualquier punto de acceso a aws. 
- Desde la consola de aws (consola desde administración)
- Desde el cliente 
- Desde  un sdk (Bibiloteca / Aplicaciones de desarollo por medio de las cuales me puedo conectar a aws.)
- Monitoriza Acciones de almacenamiento / análisis y reparación. 

Podemos buscarlo desde la consola de aws como: ``CludTrail``

Podemos ingresar ``CludTrail>Historial de Eventos``

Podemos presionar cualquier evento para ver su contenido. 
Contiene: Descripción general - Recursos asociados. 

Por ejemplo una actividad: 

AssociateDefaultView : es realizada por un usuario **onboarding** EN ESTE CASO: “onboarding” no es un usuario humano, sino una identidad de servicio (service user) creada por AWS para realizar acciones iniciales o automatizadas durante la fase de configuración o incorporación (onboarding) de la cuenta o recursos. 

Inicialmente veremos muchas actividades realizadas **onboarding** automaticamente por un usuario de aws. 


Ofrece ademas este Registro de enventos en el historial. 

``CludTrail>Historial de Evento`` : Puedo filtrar eventos / por tipo de recurso , usuario que lo utliza , fecha del evento. Y los filtros para información queremos ver tambien podemos verlo. 

En resumen: **``CloudTrail``**:  Análiza que se hace / Donde / Y a quien afecta (Quien lo hizo )


### Recordar paquetes de conformidad. 
Son paquetes de medidas que podemos implmentar y utilizamos unas plantillas de muestra. 

Hay una serie de recopilaciones , de medidas de seguridad que queremos cumplir o que podemos cumplir. Ejmplo : Al buscar S3 nos aparece esta recopilación de mejores practicas para S3. 