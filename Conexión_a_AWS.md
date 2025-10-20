# Formas de conexión.

1. **Red publica internet.** Tenemos un método físico de conexión a nuestro proveedor y llegará fisicamente a los servidores de amazon. Empieza en un origen y llega a su destino. 

La conexión no cifra los paquetes, si los protocolos (HTTPS), pero la conexión no está cifrada no tenemos ningun control y eso la hace la forma menos segura.

2. **VPN** ``Físiciamente la conexion todavia no está cifrada``, no podemos controlarla aún, pero vamos a usar una (VPN) , una red privada virtual, una conexión que va a crifrar estos datos, no mediante un protocolo concreto sino que la propia conexión ya está cifrada de punto a punto, los paquetes no se podran ver porque si algien los intercpeta van a estar cifrados. La propia conexión va a ir cifrada , y solo se destapan en el punto de destino. 

**NO ES** lo mismo ``cifrar una conexión (VPN) Virtual private network`` que una conexión que utiliza un protocolo que usa una conexión cifrada. Amazon nos indica como establecer esta vpn. 

3. **Conexión física de amazon** No nos servimos de las conexiones de intener, sino que un proveedor especifico , donde aws controla todo, la infraesturctura , servidores, conexión, todo es ajeno jamas pasa por ninguna infraestrcutura publica. Sino que **AWS Direct Conect** estlece una conexión más privada.

Nos ofrece un cliente para poner origen y destino. Orientado a empresas. Se requiere un socio de entrega, y como ventajas tiene multiples opciones de cifrados, y ventajas de rendimiento. El punto de trabajo está conectado a la infraestrcutura física de AMAZON. 
