# Análisis de tráfico con Wireshark



![Imagen de portada](./imagenes/wire.jpg)



Trabajo realizado por:

```

	- Silvia Cazalla Bazán
	- Jose María López Serrano

``` 


**Índice**
 
	1. [Introdución.](#introduccion)
		1.1. [Justificación.](#justificacion)
	2- Utilidades analizador de red (Wireshark).
	3- Metodología
		3.1- Reconocimiento y clasificación de los paquetes.
		3.2- Filtros para la observación del tráfico deseado en las redes.
		3.3- Escaneo y enumeración de puertos en la red.
		3.4- Análisis, gráficos y estadisticas de los paquetes de datos.
	4- Importancia de la seguridad en los paquetes de datos para evitar ataques.
	5- Cifrado, encriptación (seguir desarrollando puntos trabajo).
	6- ...
	7- ...
	8- ...
	9- ...


<div id = 'introduccion'/>
## 1- Introducción:


La complejida que estan alcanzando las redes informáticas y la exigencia en cuanto a 
la operación con las mismas es cada vez más grande y difícil para trabajar con ellas.
Además que estas redes cada vez deben ser capaces de soportar más tráfico entre las
máquinas, más servicios y programas...etc, por tanto es una labor importante monitorear
las redes evitando posibles problemas que puedan surgir, mejorando la calidad del servicio
para los usuarios en la red.

Wireshark implementa una amplia gama de filtros que facilitan la defnición de criterios de 
búsqueda para más de 1100 protocolos soportados actualmente, contando con una interfaz 
gráfica fácil e intuitiva. 

De este modo tambien conocer el trafico que concurre y su protocolo, para
evitar colapsos con trafico no deseado, mejorando el rendimiento de la red, facilitando el 
almacenamiento y procesamiento de la información ya que nos permite compartir datos, de 
igual manera nos permite establecer los recursos a los que se puedan acceder en la red.


# 1.1- Justificación:<a name="justificacion"></a>

Wireshark es un software de grandes capacidades para el manejo de redes, soporta varios 
protocolos entre otras cualidades que se describirán a lo largo del trabajo.
Además cuenta con todas las características estándares de un analizador de protocolos y 
lo más importante es de licencia libre.

Otra motivación que nos hizo elegir el tema de trabajo de análisis de tráfico en 
Wireshark es que las redes son un tema de interés para nosotros y hemos trabajado 
bastante con ellas en nuestra universidad de origen.

Con este trabajo se pretende dar a conocer las funcionalidades básicas en el análisis y
captura de paquetes en una red mediante Wireshark a los usuarios interesados en las redes.
 

## 2- Utilidades analizador de red (Wireshark):

Antes de empezar a aprender como podemos analizar y filtrar el tráfico deseado, es importante
saber la multitud de utilidades que posee wireshark.
Este analizador de red puede ayudarnos en:

´´´
	- Detección de intrusos en nuestra red.
	- Descubrir cuellos de botella, con el análisis de rendimiento.
	- El análisis de las operaciones de las aplicaciones.
	- Descubrir origen de la denegación de servicios o los virus.
	- Resolución de problemas en la red.

´´´


