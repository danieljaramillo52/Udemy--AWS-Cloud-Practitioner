# Proceso de la nube. 

1. Proceso básico : Servidor físico - autoadministrado adquirido (Hardware)

Se conecta por medio de un dominio .pcox.com (Servidor web / Servidor de correo. ) Y se conecta a estwe servidor para acceder a los servicios de un dominio. 

Se ubicaban fìsicamente esos datos. 

2. Proceso actual:  La nube se asocia a un conjunto de servidores. 

---

### Comparativa: 

**Procesao básico** : Compras un auto. (Tu servidor)

**Proceso actual** : Alquilas un auto / conjutno de autos / En el caso de la nube la infraestrctura.  (El paradigma ahora es "alquilar" una parte de infraestrctura para poder montar servicios.) 

AWS - AZURE - ORACOLE ...


### Computación en la nube. 
Es el uso de una red de servidores remotos conectados a internet para almacenar , administrar , procesar datos , sevidores , bases de datos etc... 

---

### Ventajas de la computación en la nube. 

Modelo propio : **ON PREMISE.** 

Debes montar toda la infractuctura física e informatica (Con todos sus costos).

Modelo de servicios : **CLOUD COMPUTING**

| Aspecto                         | On Premise                                                                                     | Cloud                                                                                              |
|---------------------------------|-------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------|
| **Costos**                      | Costes fijos de hardware, inversión inicial muy elevada.                                        | Pago por uso: solo se paga lo que se consume.                                                     |
| **Precios de usuario**           | Precios de adquisición completos por usuario final (más costoso, tarifa íntegra).               | Precios más accesibles gracias a la economía de escala de los grandes proveedores.                |
| **Dimensionado y escalado**     | Debe dimensionarse desde el inicio. Escalar hacia arriba para no quedarse corto → genera pérdidas en temporadas bajas. | Escalado flexible bajo demanda: <br>• **Vertical**: aumentar potencia de un servidor.<br>• **Horizontal**: añadir más servidores. |
| **Tiempo de aprovisionamiento** | Solicitud y trámites largos: pedir recursos, instalarlos, depender de la infraestructura.       | Entrega inmediata: aprovisionamiento automatizado e instantáneo.                                  |
| **Mantenimiento**               | Responsabilidad directa del centro de datos físico: sistemas, trabajadores, disponibilidad.     | Mantenimiento externalizado: garantizado por el proveedor, incluido en el servicio.               |
| **Problemas para despliegues mundiales** | Si se comunica con un servidor nuestro, como hacemos el despliegue para usuarios de todo el mundo. Subcontratar empresar intregar recursos , balancear carga, gran problema. | Con los provedores cloud nos beneficiamos de la gran de red de infraestrutura del proveedor a nivel mundial.

### **Resumen**

| Aspecto               | On Premise (propio)              | Cloud (servicios)                     |
| --------------------- | -------------------------------- | ------------------------------------- |
| **Costos**            | Alta inversión inicial.          | Pago por uso.                         |
| **Usuarios**          | Licencias completas por usuario. | Precios más bajos por escala.         |
| **Escalado**          | Difícil y lento.                 | Flexible e inmediato.                 |
| **Aprovisionamiento** | Trámites largos.                 | Recursos listos al instante.          |
| **Mantenimiento**     | Responsabilidad propia.          | Lo gestiona el proveedor.             |
| **Despliegue global** | Complejo y costoso.              | Red mundial del proveedor disponible. |


---


## **CAPEX VS OPEX**

**El gasto de capital (Capex)**: Se refiere al gasto de invesión que debemos asumir. Se asocian a adquirir hardware , componentes , servidores. Es una inversión inicial fuerte.

**El pago por uso (Opex)**: El costo para el funcionamiento de un producto de la  operación, el pago por lo que estamos usando. 


# **7RS : 7 Estrategias de Migración.** 

Se refieren a cuestiones técnicas en varios niveles, a nivel de programación o de infraestructura. En la infraestructura/programas.

Proceso de migración **ON PREMISE A CLOUD**.

1. **Retirar**: Eliminar aplicaciónes que ya no son necesarias , que no vamos a migrar a nube. 

2. **Retener**: Aplicaciones a mantener en el entornop de origen que no nos interesa migrar propiamente. O que aún no están listas para este paso. 

3. **Realohar**: Aplicaciones que simplemente vamos a migrar a la nube sin cambiar nada de la aplicación en si misma, **si cambia su entorno de despliegue** , "levantar y cambiar", por ejemplo tomar las aplicaciones e instalarlas en nuevas VM pero ya del proveedor. 

Beneficio: Las aplicaciones son más fáciles de optimizar / rediseñar una vez que ya se están ejecutando en la nube. En parte porque su organización habrá desarrollado mejores habilidades para hacerlo, y en parte porque la parte difícil (migrar la aplicación, los datos y el tráfico) ya se ha realizado.



4. **Relocalizar**: Caso especifico para aplicaciones que comprenden un gran número de servidores.  Es **mover máquinas virtuales completas (VMs)** o **incluso clusters enteros** desde el entorno On Premise (o un datacenter privado) directamente al cloud, sin hacer cambios en el sistema operativo, las aplicaciones ni las configuraciones internas. Es decir te empacas el entorno completo de despliegue 

5. **Recomprar**: Que cosas debemos comprar y que cosas dejar de comprar porque ya no nos sirven de mucho en nuestro nuevo entorno. Para aplicaciones con una versión o producto diferente y ofrece más valor que a infraestructura existente. 

6. **Replataformar**: Aplicaciones que debemos adaptar, para se optimicen mejor en su funcionamiento,  aprovechando las capacidades de aws

7. **Reformar** : Modificar la arquitectura de la aplicación para aprovevchar las caracteristicas y beneficios nativos que nos ofrece la nube. Mejora agilidad rendimiento y escalabilidad. 
