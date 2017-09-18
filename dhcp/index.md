# Servidor DHCP


El  protocolo  de  configuración  dinámica  de  host  (**DHCP, Dynamic Host Configuration Protocol**),es un estándar TCP/IP que  simplifica  la  administración  de  la  configuración  IP haciéndola automática. 
El  servidor  DHCP  recibe  peticiones  de  clientes  solicitando una  configuración  de  red  IP.  Responde  proporcionando  los parámetros que permitan a los clientes autoconfigurarse. Los clientes  hay  que  configurarlo  seleccionando  la  opción *'Obtener dirección IP automáticamente'*. El servidor DHCP proporciona la configuración red, entre los datos que ofrece:

* Dirección IP
* Máscara de red
* Dirección del servidor DNS
* Nombre DNS
* Puerta de enlace de la dirección IP
* Dirección de Publicación Masiva (broadcast address)
* MTU (Unidad de Transferencia Máxima según siglas en inglés) para la interfaz
* Servidores NTP (Protocolo de Tiempo de Red)
* Servidor SMTP
* Servidor TFTP

Al trabajar con el servidor DHCP tenemos que conocer los siguientes conceptos:

* **Ámbito  servidor  DHCP**:  Agrupamiento administrativo  de  equipos  o  clientes  de  una subred que utilizan el servicio DHCP.
* **Rango  servidor  DHCP**:  Grupo  de  direcciones IP en una subred que el servidor puede conceder a los clientes 
* **Concesión  o  alquiler  de  direcciones**:  Período de tiempo que los servidores DHCP especifican, durante el cual un equipo cliente puede utilizar una dirección IP.
* **Reserva  de  direcciones  IP**:  Direcciones  IP que se asignan siempre  a  las  mismos equipos. Es similar a configurar una dirección IP estática pero de forma  automática  desde  el  servidor  DHCP,  la  forma  de hacerlo es asociar direcciones MAC a direcciones IP. 
* **Exclusiones**: Conjunto de direcciones IP pertenecientes al rango que no se van a asignar.

**Indice**

.. toctree::
   
   enlaces
   dhcp
   cuestionario
   ejercicio1

   
