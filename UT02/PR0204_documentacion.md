```
1. 
        1. La tarea se ejecuta cada hora
        0 * * * * 

        2. La tarea se ejecuta los domingos cada 3 horas
        0 */3 * * 0

        3. La tarea se ejecuta a las 12 de la mañana los días pares del mes.
        0 12 2-30/2 * * 

        4. La tarea se ejecuta el primer día de cada mes a las 8 de la mañana y a las 8 de la tarde.
        0 8,20 1 * * 

        5. La tarea se ejecuta cada media hora de lunes a viernes.
        */30 * * * 1-5 

        6. La tarea se ejecuta cada cuarto de hora, entre las 3 y las 8, de lunes a viernes, durante todo el mes de agosto
        */15 3-8 * 8 1-5 

        7. La tarea se ejecuta cada 90 minutos

2. ¿Cómo compruebas si el servicio cron se está ejecutando?
con systemctl status cron


3. ¿Cuál es el efecto de la siguiente línea crontab?

    */15 1,2,3 * * * who > /tmp/test
Ejecuta el comando who cada 15 minutos durante la 1, 2 y 3 horas, y redirecciona la salida al archivo /tmp/test, sobrescribiendo el contenido.

4. Indica la ruta del fichero crontab del sistema
 /var/spool/cron/crontabs/

5. ¿Qué ficheros controlan los usuarios que pueden utilizar el crontab?
/etc/cron.deny y /etc/cron.allow

6. Excepcionalmente se debe iniciar una tarea llamada script.sh todos los lunes a las 07:30h antes de entrar en clase ¿Cómo lo harías?
30 7 * * 1 /script.sh


7. Se ha cancelado la tarea. ¿Cómo listar y luego, suprimir la tarea?
Para listar: crontab -l
Para suprimir la tarea: crontab -e y eliminar la linea


8. Ejecuta el comando ps -ef para el usuario root cada 2 minutos y redirecciona el resultado a /tmp/ps_result sin sobrescribir los antiguos.
*/2 * * * * ps -ef >> /tmp/ps_result


9. Verifica la lista de tareas en crontab
crontab -l


10. Espera unos minutos y comprueba el resultado en /tmp

11. Crea el usuario asir2 y prohíbele utilizar el crontab.
sudo adduser asir2
sudo nano /etc/cron.deny
luego agregar el usuario asir2

12. Verifica que el usuario asir2 realmente no puede utilizar crontab


13. Programa crontab para que cada día a las 0:05 se eliminen todos los ficheros que se encuentran en el directorio /tmp.
5 0 * * * rm -rf /tmp/*

14. Programa una tarea en el sistema que se lance de lunes a viernes a las 9 de la mañana durante los meses de verano (julio, agosto y septiembre) que escriba en un fichero la hora actual (comando date, aunque tienes que mirar la ayuda para elegir un formato comprensible) seguido del listado de usuarios que hay conectados en ese momento en el sistema (comando who)
0 9 * 7,8,9 1-5 echo "$(date '+%Y-%m-%d %H:%M:%S') - $(who)" >> /fichero

15. El servicio cron se ayuda de una serie de ficheros y directorios que se encuentran en el directorio /etc. Explica la función de cada uno de los siguientes ficheros/directorios:

cron.d: Permite la instalación de scripts de cron. Cada archivo en este directorio debe tener una sintaxis similar a un archivo de crontab.

cron.allow: Archivo que contiene una lista de usuarios permitidos para utilizar crontab. 

cron.deny: Archivo que contiene una lista de usuarios que no pueden utilizar crontab. 

cron.daily: Directorio que contiene scripts que se ejecutan diariamente.

cron.hourly: Directorio que contiene scripts que se ejecutan una vez por hora.

cron.monthly: Directorio que contiene scripts que se ejecutan mesualmente.
```