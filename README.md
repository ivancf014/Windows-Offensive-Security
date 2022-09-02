# Windows-Offensive-Security

## Acceso físico
Si tenemos acceso físico a un equipo podemos usar un USB o CD con fines malintencionados pero, que hay más allá de esto.

### BIOS
* Pila 
Si quitas la pila durante 15-20 minutos se restableceran los ajustes inlcuida la contraseña.
* Jumper CMOS
Casi todas las placas tienen un jumper que pueden resetear los ajustes, si conectamos los pines se resetearan los ajustes.
* Extra
En algunos casos si bloqueamos el acceso a la BIOS fallando la contraseña, nos da un código de error que si nos vamos a la página BIOS Password Recovery e introducimos el código se puede conseguir el código de acceso universal para acceder al equipo.

### UEFI
Existen herramientas que permiten comprobar la seguridad de los sistemas UEFI como puede ser CHIPSEC.

### Memoria RAM
* Cold boot
Este ataque consiste en enfriar la memoria RAM para aprovechar sus datos. Gracias al material con el que están fabricadas las memorias sus datos siguen en ellas 1 o 2 minutos después del apagado del equipo, si se enfrian podriamos conseguir que esos datos duren hasta 10 minutos en ellas. Después realizariamos un volcado de memoria con una aplicación como DumpIt, Memoryze o dd.exe entre otras.

### Modificando la SAM
La SAM es un archivo que tienen los sistemas Windows que almacena información sobre usuarios y contraseñas locales. Con la herramienta 'chntpw'se puede visualizar y editar la información.

### Rubber Ducky
Quizás este es el Pendrive más conocido pero existen muchos otros, con él podríamos robar contraseñas wifi, cookies, capturas del escritorio, agregar usuarios con permisos administrativos, descarga de software de internet etc.

### PowerShell
Desde PowerShell podemos ejecutar payloads para obtener acceso al equipo, por ejemplo tenemos la herramienta SET que nos facilita la vida. A veces nos vamos a encontrar con que tenemos restricciones a la hora de ejecutar un script, para ello tenemos que realizar un bypass a la política de ejecución.
Podemos copiar el contenido del script en la consola, utilizar el argumento '-command', utilizando el comando echo con el contenido del script y pasarlo a través de un pipe.

### Kon-Boot
Esta herramienta permite acceder al equipo como usuario con maximos privilegios.

## Escalada de privilegios

### Unquoted Service Paths
Los servicios de Windows tienen una ruta de acceso a su ejecutable, si esta ruta no está citada de la manera correcta podría ser vulnerable a una escalada de privilegios. Si un atacante tiene permiso de escritura sobre esa carpeta puede colocar un programa malicioso en la ruta principal.

### Permisos mal configurados
En Windows la información sobre los servicios se almacena en 'HKLM\SYSTEM\CurrentControlSet\Services', sin embargo es posible verla también en 'HKLM\SYSTEM\ControlSet001\Services' 








