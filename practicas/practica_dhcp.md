# Práctica: Servidor DHCP 

```eval_rst
.. note::

	**(16 tareas - 25 puntos)(7 tareas obligatorias - 11 puntos)**

.. note::

	* Muestra al profesor: Tarea 4, Tarea 7, Tarea 13, Tarea 14
```

## Teoría

```eval_rst
.. note::

	* **Tarea 1 (1 punto):** Lee el documento `Teoría: Servidor DHCP <http://serviciosgs.readthedocs.io/es/latest/dhcp/dhcp.html>`_ y explica el funcionamiento del servidor DHCP resumido en este `gráfico <http://serviciosgs.readthedocs.io/es/latest/_images/dhcp.png>`_.	
```

## DHCPv4

### Preparación del escenario

Crea un escenario usando Vagrant que defina las siguientes máquinas:

* Servidor: Tiene dos tarjetas de red: una pública y una privada que se conectan a la red local.
* nodo_lan1: Un cliente conectado a la red local.

### Servidor dhcp

Instala un servidor dhcp en el ordenador "servidor" que de servicio a los ordenadores de red local, teniendo en cuenta que el tiempo de concesión sea 12 horas y que la red local tiene el direccionamiento 192.168.100.0/24.

```eval_rst
.. warning::

	* **Tarea 2 (1 punto)(Obligatorio):** Entrega el fichero Vagrantfile que define el escenario.
	* **Tarea 3 (3 puntos)(Obligatorio):** Muestra al profesor el servidor DHCP funcionando. Muestra el fichero de configuración del servidor, la lista de concesiones, la modificación en la configuración que has hecho en el cliente para que tome la configuración de forma automática y muestra la salida del comando `ifconfig`.
	* **Tarea 4 (2 puntos):** Muestra al profesor el servidor funcionando como router y NAT, de esta forma los clientes tendrán internet.
	* **Tarea 5 (1 punto):** Realizar una captura, desde el cliente usando **tcpdump**, de los cuatro paquetes que corresponden a una concesión: DISCOVER, OFFER, REQUEST, ACK.
```

### Funcionamiento del dhcp

```eval_rst
.. warning::

	Vamos a comprobar que ocurre con la configuración de los clientes en determinadas circunstancias, para ello vamos a poner un tiempo de concesión muy bajo. Muestra los resultados al profesor.	

	* **Tarea 6 (2 punto):** Los clientes toman una configuración, y a continuación apagamos el servidor dhcp. ¿qué ocurre con el cliente windows? ¿Y con el cliente linux?
	* **Tarea 7 (2 punto)(Obligatorio):** Los clientes toman una configuración, y a continuación cambiamos la configuración del servidor dhcp (por ejemplo el rango). ¿qué ocurriría con un cliente windows? ¿Y con el cliente linux?
```

### Reservas

Crea una reserva para el que el cliente tome siempre la dirección 192.168.100.100.

```eval_rst
.. warning::

	* **Tarea 8 (2 puntos)(Obligatorio):** Indica las modificaciones realizadas en los ficheros de configuración y muestra al profesor una comprobación de que el cliente ha tomado esa dirección.
```

### Uso de varios ámbitos

Modifica el escenario Vagrant para añadir una nueva red local y un nuevo nodo:

* Servidor: En el servidor hay que crear una nueva interfaz
* nodo_lan2: Un cliente conectado a la segunda red local.

Configura el servidor dhcp en el ordenador "servidor" para que de servicio a los ordenadores de la nueva red local, teniendo en cuenta que el tiempo de concesión sea 24 horas y que la red local tiene el direccionamiento 192.168.200.0/24.

```eval_rst
.. warning::

	* **Tarea 9 (1 punto)**: Entrega el nuevo fichero Vagrantfile que define el escenario.
	* **Tarea 10 (1 punto)**: Explica las modificaciones que has hecho en los distintos ficheros de configuración. Entrega las comprobaciones necesarias de que los dos ámbitos están funcionando.
	* **Tarea 11 (1 punto)**: Realiza las modificaciones necesarias para que los cliente de la segunda red local tengan acceso a internet. Entrega las comprobaciones necesarias.
```

## DHCPv6

### SLAAC

Vamos a usar el primer escenario para configurar en el cliente el programa `radvd` para comprobar como los clientes se autoconfiguran con una dirección ipv6 (SLAAC (Stateless Address Autoconfiguration)). Vamos a trabajar con el prefijo `2001:abcd::/64`.

```eval_rst
.. warning::
	* **Tarea 12 (1 punto)(Obligatorio):** Configura de manera adecuada en el servidor el programa `radvd` y comprueba que los clientes (Linux y Windows) se configuran coun ipv6 global.
	* **Tarea 13 (1 punto)(Obligatorio):** Configura `radvd` para entregar también el servidor DNS (RDNSS) y el campo *search* (SNSSL). Comprueba qué esos datos lo configura el cliente Linux. ¿Y el cliente Windows?
```

### DCHPv6

Configura en el servidor isc-dhcp-server una zona para repartir los siguientes elementos:

* Un rango de direcciones: `2001:abcd::1000` hasta `2001:abcd::2000`
* El DNS y el campo *search*.

```eval_rst
.. warning::
	* **Tarea 14 (2 puntos)(Obligatorio):** Configura de manera adecuada en el servidor dhcpv6 y comprueba que los clientes (Linux y Windows) se configuran con ipv6 global.
	* **Tarea 15 (1 punto):** Configura una reserva para que el cliente linux se configure con la dirección `2001:abcd::a`.
```
### Delegación de prefijo (PD)

En nuestra red tenemos un servidor DHCPv6 puede repartir un prefijo cuando se realiza una petición (es decir cuando se solicita el prefijo), esto nos puede servir para crear un router dentro de nuestra red interna que reparta direcciones ipv6 con un determinado prefijo.
```eval_rst
.. warning::
	* **Tarea 16 (3 puntos):** Configura en tu servidor un cliente dibbler-dhcp que es capaz de recoger el prefijo delegado por nuestro servidor `macaco`. Condigura `radvd` para que reparta direcciones con ese prefijo. Comprueba que los clientes (Linux y Windows) se configuran con ipv6 global. Realiza un ping desde el cliente a la dirección `2001:ccba:470::1` que es la de macaco.
```
