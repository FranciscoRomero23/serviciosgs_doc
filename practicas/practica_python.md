# Práctica: Ejecución de script Python. Rendimiento.

```eval_rst
.. note::

    (6 tareas - 15 puntos)(3 tareas obligatorias - 6 puntos)
```
    
Vamos a comparar el rendimiento de distintas configuraciones de servidores web sirviendo páginas dinámicas programadas con Python, en concreto vamos a servir un CMS Mezzanine (Instala algunas páginas de demostración durente la instalación: Would you like to install some initial demo pages?).

Las configuraciones que vamos a realizar son las siguientes:
	
* apache2 + Módulo wsgi
* apache2 + gunicorn
* apache2 + uwsgi
* nginx + gunicorn
* nginx + uwsgi

```eval_rst
.. note::

		Apache2
		-------

	    * **Tarea 1 (2 puntos)(Obligatorio)**: Documenta la instalación del módulo wsgi de apache2. Muestra los ficheros de configuración y muestra la ejecución del CMS.
	    * **Tarea 2 (2 puntos)(Obligatorio)**: Documenta la instalación y configuración de gunicorn y apache2. Muestra mezzanine funcionando y una comprobación de que, efectivamente, se está usando gunicorn.
	    * **Tarea 3 (2 puntos)(Obligatorio)**: Documenta la instalación y configuración de uwsgi y apache2. Muestra mezzanine funcionando y una comprobación de que, efectivamente, se está usando wusgi.
	    
	    nginx
	    -----

		* **Tarea 4 (2 puntos)**: Documenta la instalación y configuración de gunicorn y nginx. Muestra mezzanine funcionando y una comprobación de que, efectivamente, se está usando gunicorn.
	    * **Tarea 5 (2 puntos)**: Documenta la instalación y configuración de uwsgi y nginx. Muestra mezzanine funcionando y una comprobación de que, efectivamente, se está usando wusgi.
```

## Estudio de rendimiento

Ahora utilizando el script [benchmark.py](https://github.com/josedom24/serviciosgs_doc/blob/master/rendimiento/benchmark.py), realiza las pruebas de rendiemento para cada una de las configuraciones anteriores.

```eval_rst
.. note::

	    * **Tarea 6 (5 puntos)**: Entrega la configuración del script de pruebas para cada una de las configuraciones. Entrega los datos obtenidos y la gráfica que has generado.
```

