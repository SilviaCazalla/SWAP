##Práctica 3:
#Balanceadores de carga.

En esta práctica hemos creado dos máquinas virtuales nuevas de modo, que cada una tiene una configuración como 
balanceador. La nueva máquina virtual "Maq3Balanceador" en la que hemos configurado el balanceador tipo
haproxy, con ip 192.168.73.132, con lo cual puede distribuir las distintas peticiones que se hagan desde el 
pc externo hacia las máquinas virtuales 1 y 2, creadas en la práctica anterior.
Se comprueba que distribuye las distintas peticiones con curl.

añadir aqui imagen comando top con haproxy


En la máquina virtual "Maq4" hemos configurado el balanceador de tipo nginx, con ip 192.168.73.133, que se encarga
de hace lo mismo que haproxy con las máquinas virtuales de la práctica 2.
Con respecto a la configuración de nginx tuvimos problemas y no realizaba la distribución de carga, es más 
al intentar lanzar el balanceador haproxy nos daba error.

añadir foto fallo nuestro

El fallo estaba en default.config, el cual solucionamos con ayuda del profesor y pudimos comprobar como el nuevo 
balanceador de tipo nginx distribuye carga al realizar varios 'curl' a esta máquina desde el pc externo.

añadir foto balanceador haciendo top bien


