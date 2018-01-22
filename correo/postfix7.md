# Soluciones al problema del spam


Como hemos visto en el caso 3 es posible que nuestra ip dinámica que tenemos en casa sea rechazada por los servidores de correo. En este apartado vamos a ver distintas técnicas que nos permiten luchar contra el spam y que nos pueden permitir que nuestro correo llegue a su destino y no sea rechazado. Veamos las posibles técnicas:

* **SMTP submission**: Para que no se permita conectar directamente a un servidor de correo de destino, una técnica para evitar a los spammer sería cambiar el puerto estándar del protocolo SMTP, normalmente se cambia al 587. Para más información leer el siguiente artículo: [Para que el correo llegue a buen puerto](http://blog.arsys.es/para-que-el-correo-llegue-a-buen-puerto/)

* **Enviar correo a través Relay autentifcado**: En este caso podemos hacer relay uslizando un servidor de correos autentificado por ejemplo gmail: [Configurar postfix a través de un relay host autenticado (Gmail)](http://albertomolina.wordpress.com/2009/01/04/configurar-postfix-a-traves-de-un-relay-host-autenticado-gmail/)

* **SMTPd restrictions**: Podemos configurar nuestro servidor de correos para que filtre a los clientes que intentan usarlo por medio de algún parámetro del protocolo: HELO, MAIL FROM, RCPT TO,..., en el siguiente artículo puedes informarte sobre esta técnica y algunas otras que vamos a ver a continuación: [SMTPd restrictions, SPF, DKIM and greylisting ](https://workaround.org/ispmail/wheezy/smtpd-restrictions-spf-dkim-and-greylisting)

* **Realtime blacklists (RBL)**: La técnica más importante para luchar contra el spam son las listas negras. Podemos configurar nuestro servidor de correo para que consulte en las distintas listas que existen la dirección de ip de origen. Tenemos muchos sitios para ver si nuestra ip está en una lista negra:
	* [mxtoolbox ](http://mxtoolbox.com/blacklists.aspx)
	* [Spamhaus Block List ](http://www.spamhaus.org/sbl/index.lasso)
	* [Cisco IronPort SenderBase Security Network ](http://www.senderbase.org/)

* **Sender Policy Framework (SPF)**: Esta técnica consiste en publicar una serie de datos en un registro TXT del servidor DNS que haga que el servidor de correo donde llega el correo confíe en que el correo no es spam. Para más información lee el artículo: [Sender Policy Framework (SPF)](https://github.com/josedom24/serviciosgs_doc/raw/master/correo/doc/SPF.pdf)
	* **DomainKeys Identified Mail (DKIM)**: Es un mecanismo que nos permite firmar un correo utilizando criptografía de clave pública. Para más información puede leer en la wikipedia: [DomainKeys Identified Mail](https://es.wikipedia.org/wiki/DomainKeys_Identified_Mail) 
	* **Lita gris**: El servidor de correo si determina que el origen puede ser una amenaza, rechazada por defecto el correo, los servidores de correo legítimos volverán a enviar el correo transcurrido un tiempo, este correo será aceptado. Sin embargo un sistema que manda spam no suele reenviar el correo rechazado. Para más información puede leer en la wikipedia: [Lista gris](https://es.wikipedia.org/wiki/Lista_gris) 

Para terminar os dejo una presentación: [Univ. de Deusto: Seguridad en sistemas de correo electrónico](http://www.slideshare.net/alvmarin/seguridad-en-sistemas-de-correo-electrnico-3131736)