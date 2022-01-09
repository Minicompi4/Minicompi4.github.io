## Activar modo monitor en Kali/Parrot.


```markdown 
Lo primero que necesitamos hacer es saber cual es nuestra tarjeta Wireless 
Utilizaremos el siguiente comando :   #iwconfig 

Como referencia usaremos #wlan0

Abriremos una terminal y escribiremos los siguientes comandos:

#airmon-ng start wlan0

Para activar la placa en modo monitor


#ifconfig wlan0mon down

Para desmontar la tarjeta wireless


#iwconfig wlan0mon mode monitor

Para activar la tarjeta wireless en modo monitor


#ifconfig wlan0mon up 

Para montar la tarjeta wireless en modo monitor


Ahora estará lista para su uso.
```

#Volver -> [click](https://minicompi4.github.io)
