# AWS Lambda. 

Queremos una manera de ejecutar nuestras funciones. (**serverless**) No queremos preocuparnos por el servidor. 

Lambda: Es un servicio de AWS que proporciona un entorno para ejecutar nuestras funciones. Es un servicio de ejecución de código que incluye: 

- Funcionalidades de tolerancia a errores 
- Escalado Automático
- Compatible con multiples lenguajes C++ , C#, Node Js , Ruby, y Go, Python , PHP 

No nos preocupamos de donde se ejecuta, recursos pa aprovisionar subir el código. 
De forma nativa solop subimos el código. 

# Creamos el código lambda. 

La subimos a AWS, y vamos a decidir como se ejecuta ? Por medio de eventos, los **eventos** son disparaderos que hacen que se ejecute la función. Por ejemplo tareas rutinarias, procesar imagenes, ``Solo cuando se desaten estos eventos, aquí y solo aquí se utilizan y consumen los recursos`` Y nunca más. (Solo se paga por el tiempo de computo, se se utiliza 1 segundo , 10 segundos , 30 segundos. Pagamos por eso. )


**No necesitamos un servidor siempre a la escucha**

### 💡 **Resumen rápido**

| 🧩 Tipo de evento        | 🪣 Ejemplo de origen        | ⚙️ Acción típica de Lambda             |
|---------------------------|-----------------------------|----------------------------------------|
| **S3**                    | Subida o eliminación de archivos | Procesar o mover datos                |
| **DynamoDB**              | Actualización de registros      | Sincronizar o validar datos           |
| **SQS / SNS**             | Llegada de mensaje o notificación | Procesar tareas en lote               |
| **API Gateway**           | Petición HTTP o WebSocket       | Backend sin servidor                  |
| **EventBridge / CloudWatch** | Cron programado o evento del sistema | Limpieza, informes o automatización   |
| **Cognito**               | Registro o login de usuario     | Enviar correo o validar información   |
| **Kinesis**               | Flujo de datos en tiempo real   | Analizar o transformar datos          |
| **CloudTrail / Config**   | Cambio en la infraestructura AWS | Auditoría o alertas automáticas       |

## Límites de lambda. 

- 1000 ejecuciones simultaneas

- 75 gb de almacenamiento para subir (codigo librerias por ejemplo)

- Limite de memoria 128 mb a 10240 mn

- Como mucho **Una función lambda se puede tardar un maximo de 15 min** (900 segundos)

- Ojo con tiempos de lectura y escritura. 


-> Lamda forma parte de la capa gratuita. (1 millon de solicitudes gratis. )

Revisar precios. 