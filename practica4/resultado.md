## Práctica 4:

# Certificado SSL autofirmado

Generamos un certificado SSL autofirmado en Ubuntu Server.

Para ello activamos el módulo SSL de Apache, y generamos el certificado en nuestra máquina principal 
(MACHINE2) y específicamos la ruta a los certificados en la configuración.

Completamos los datos que nos pide para configurar el dominio, editamos el archivo default-ssl, activamos 
el sitio default-ssl y reiniciamos apache.

Para comprobar la petición por HTTPS utilizamos un curl -k.

A continuación copiamos los archivos .crt y .key del certificado a las demás máquinas de la granja para usar el
mismo certificado en toda nuestra granja web.

En el servidor secundario activamos el sitio default-ssl y reiniciamos apache.

En el balanceador nginx ponemos la ruta a la carpeta que contiene estos archivos, configuramos el archivo default.conf 
de nginx y reiniciar.

* Hemos tenido un problemas con nuestro balanceador nginx anterior (MAQUINA4) y tuvimos que volver a preparar un 
balanceador nginx en MAQUINA3 para solucionar el contratiempo.

* Hemos tenido problemas para copiar el certificado de MACHINE2 a las demás máquinas y decidimos enviarlo en correo 
y movido a una carpeta del sistema con: 

```

cp apache.key etc/apache2/SSL
cp apache.crt etc.apache2.SSL.

```

* Para completar la conexión HTTPS con la máquina secundaria (MAQ1) hemos habilitado el servicio MOD_SSL con: 

```

sudo a2enmod ssl y sudo a2ensite default-ssl.conf

```

Después de esto podemos ver como el curl funciona para cualquier máquina de nuestra granja.

# Configuración del cortafuegos con IPTABLES

Procedemos a crear un script activar-cortafuegos en /etc y ejecutamos el comando siguiente comando para que se ejecute al inicio 
del sistema:

```

chmod +x /etc/activar-cortafuegos

```

A continuación editamos el archivo /etc/rc.local para añadir la ruta de nuestro script.
