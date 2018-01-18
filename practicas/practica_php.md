# Práctica: Ejecución de script PHP. Rendimiento.

```eval_rst
.. note::

    (9 tareas - 20 puntos)(8 tareas obligatorias - 15 puntos)
```
    
Vamos a comparar el rendimiento de distintas configuraciones de servidores web sirviendo páginas dinámicas programadas con PHP, en concreto vamos a servir un CMS Wordpress.

Las configuraciones que vamos a realizar son las siguientes:
	
* Módulo php5-apache2
* PHP-FPM + apache2
* PHP-FPM + nginx 
	
```eval_rst
.. note::

		Apache2
		-------

	    * **Tarea 1 (1 punto)(Obligatorio)**: Documenta la instalación del módulo php de apache2. Muestra wordpress funcionando con el módulo php de apache2. Realiza una comprobación de que, efectivamente, se está usando el módulo php.
	    * **Tarea 2 (1 punto)(Obligatorio)**: Documenta la instalación y configuración de FPM-PHP y apache2 (escuchando en un socket UNIX) con el módulo de multiprocesamiento event. Muestra wordpress funcionando con FPM-PHP. Realiza una comprobación de que, efectivamente, se está usando FPM-PHP.
	    * **Tarea 3 (1 punto)(Obligatorio)**: Cambia la configuración anterior para que PHP-FPM escuche en un socket TCP.
	    

	    nginx
	    -----

	    * **Tarea 4 (1 punto)(Obligatorio)**: Documenta la instalación y configuración de PHP-FPM y nginx (escuchando en un socket UNIX) con el módulo de multiprocesamiento event. Muestra wordpress funcionando con PHP-FPM. Realiza una comprobación de que, efectivamente, se está usando PHP-FPM.
	    * **Tarea 5 (1 punto)(Obligatorio)**: Cambia la configuración anterior para que PHP-FPM escuche en un socket TCP.
```

## Estudio de rendimiento

Ahora utilizando el script [benchmark.py](https://github.com/josedom24/serviciosgs_doc/blob/master/rendimiento/benchmark.py), realiza las pruebas de rendiemento para cada una de las configuraciones anteriores:

* Módulo php5-apache2
* FPM-PHP + apache2 (escuchando en un socket UNIX o en un socket TCP)
* FPM-PHP + nginx (escuchando en un socket UNIX o en un socket TCP)

```eval_rst
.. note::

	    * **Tarea 6 (5 puntos)(Obligatorio)**: Entrega la configuración del script de pruebas para cada una de las configuraciones. Entrega los datos obtenidos y la gráfica que has generado.
```

## Aumento de rendimiento

```eval_rst
.. note::

		* **Tarea 7 (2 puntos)(Obligatorio)**: Añade a la configuración ** ganadora del punto anterior** memcached. Documenta la instalación y configuración memcached. Recuerda que para que Wordpress utilice memcached le tenemos que instalar un plugin. Muestra las estadísticas de memcached después de acceder varias veces a wordpress para comprobar que esa funcionando.
	    * **Tarea 8 (3 puntos)(Obligatorio)**: Configura un proxy inverso - caché Varnish escuchando en el puerto 80 y que se comunica con el servidor web por el puerto 8080. Entrega y muestra una comprobación de que varnish está funcionando con la nueva configuración.
```

## Estudio de rendimiento

A continuacion hacemos el estudio de rendimiento para las siguientes configuraciones:

* Configuración ganadora
* Configuración ganadora + memcached
* Configuración ganadora + varnish

```eval_rst
.. note::

	    * **Tarea 9 (5 puntos)**: Entrega la configuración del script de pruebas para cada una de las configuraciones. Entrega los datos obtenidos y la gráfica que has generado.
```
