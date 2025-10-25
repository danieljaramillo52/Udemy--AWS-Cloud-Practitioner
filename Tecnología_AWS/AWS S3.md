# AWS S3. 

- Almacenamiento de uso mas generico y común.

- Los datos se ALMACENAN A NIVEL DE OBJETOS CONCRETOS Y COMPLETOS. 

- No se puede almacenar a nivel de bloques como los EBS (elastic block storage).

- Estos objetos, se alamcenan dentro de **bloques (buckets)** dentro de este van los ficheros.

- Un bucked se asocia a una región y posee una copia de seguridad que se replica de forma automatica dentro de ella.

- Almacenamiento automático, y escalado casí ilimitado. 

- Un solo **elemento  == objeto**, tiene un tamaño maximo de **5TB**

- Acceso a buckets, objetos, Podemos acceder desde cualquier parte del mundo y en cualquier momento con el uso de una simple url. 

- Diseñado para ofrecer un 99.9999999% de fiabilidad.

- AWS ofrece una gamma completa de controles de seguridad , podemos detemrinar permisos para acceder, asignarle roles etc. 

- Costes:
    1. Por la cnatidad de datos GB de almacenamiento utilizadas al mes. 
    2. Por transferencia **saliente** de datos entre regiones
    3. Por solicitudes PUT , COPY , GET LIST , POST. utulizar esos datos.

- No coste por:
    1. Por las transferencias de datos  entrantes ( Enviar datos a amazon s3)
    2. Por las trnaferencias de datos  salientes a Amazon Cloud Front ó a **Instancias de EC2 vinculados a la misma región**

    (Eso significa que es conveniente tener una instancia de EC2 y la instancia de S3 dentro de la misma region para ahorrar costos.)

🧩 Qué significa “objeto” en S3

En Amazon S3, cada cosa que guardas (un archivo, una foto, un backup, un CSV, etc.) se llama objeto.
Y ese objeto está compuesto por tres partes:

🧱 Los datos → el contenido real del archivo (por ejemplo, una imagen o un video).

🏷️ Una clave (key) → el nombre o la ruta del archivo dentro del bucket.

🧾 Metadatos → información adicional (por ejemplo, tipo de archivo, fecha, permisos, etiquetas, etc.).

📦 Entonces, un **“objeto” = un archivo individual**

Cada archivo que subes a S3 se guarda como un objeto independiente, y cada uno puede pesar hasta 5 TB como máximo.

