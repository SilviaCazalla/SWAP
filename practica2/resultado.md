#Práctica2:
##
Creamos un tar con ficheros locales en un equipo remoto.
tar:fichero comprido
	* tar czf -/desktop | ssh usuario@ipdestino 'cat>~/tar.tgz'

![Imagen comando tar](/mnt/c/users/silvia/desktop/P2-CLONAR.jpeg) 

https://github.com/SilviaCazalla/SWAP/blob/master/practica2/P2-CLONAR.jpeg?raw=true

Instalamos la herramienta rsync
	* sudo apt-get install rsync

Hacemos que el usuario sea el dueño de la carpeta donde reciben los archivos que hay en el espacio web en ambas maquinas

	* sudo chown -R usuario:usuario /var/www

Para poder ver los directorios en forma de arbol:

	* sudo apt install tree

Para probar rsync clonamos una carpeta:
	
	* rsync -avz -e ssh IPdestino:/var/www/ /var/www/

Lo comprobamos con: 
	* ls -la /var/www/

/
/
/
/
/
/

Indicamos que archivo copiar y cuales no para que no se sobreescriban todos los archivos con:

	* rsync  -avz --delete --exclude=**/stats --exclude =**/ error -- exclude=**/files/pictures -e ssh maquina1:/var/www/ /var/www/
				
		(excluyendo /var/www/error, /var/www/stats... etc)

Usamos rsync para mantener las máquinas actualizadas. Para que no nos pida la contraseña al conectarnos por ssh:
	
	* ssh-keygen -b406 -trsa
		(para generar la clave)
	* chmod 600~/.ssh/authorized_keys
		(para copiar la clave pública al equipo remoto)
Copiamos la clave existente a la máquina principal (a la que queremos acceder desde la secundaria). Hemos elegido MAQ1.

	* ssh-copy-id IPmaq1

Ahora podemos conectarnos por ssh sin contraseña.
 ________________________________
<
<
<
<
<
<
<
<
<________________________________

	# En este punto tuvimos un problema con MAQ2, ya que anteriormente instalamos otra máquina con otra versión de ubuntu y con el mismo. 
		Aunque habia sido borrada desde VMWare, cuando entramos a MAQ2 encontramos la máquina antigua.
	# Volvemos a instalar y configurar una máquina nueva siguiendo todos los pasos con el nombre MACHINE2 para no volver a tener este problema.

Para ejecutar comandos añadiremos al final del comando ssh.

PROGRAMAR TAREAS CON CRONTAB

Administración de procesos en segundo plano que los ejecuta en el instante indicado en el fichero crontab.
Cron se ejecuta en background revisando la tabla del fichero /etc/crontab.

Editamos el fichero con:
	* sudo nano crontab

Establecemos una tarea en cron para mantener actualizado el contenido del directorio.

Primero probamos a cada minuto para comprobarlo más rapidamente y al ver que funciona lo dejamos a cada hora.

/****************
/
/
/
/
*****************
