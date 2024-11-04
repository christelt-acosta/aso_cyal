1.-
    -0 * * * * 
    -0 */3 * * 0 
    -0 12 */2  * *
    -0 8,20 1 * *
    -*/30 * * * 1-5
    -*/15 3-8 * 8 1-5
    -*/90 * * * *

2.-







3.-

Cada quince minutos entre la 1 y las 3 quien tiene la sesión iniciada y que se escriba en /tmp/test

    1- cat /etc/crontab
    2- 
    3- 30 7 * * 1 /home/vagrant/script.sh 
    4- crontab -r 
    5- */2 * * * * sudo ps -ef >> /tmp/ps_result
    10- 5 0 * * * rm - r /tmp
    11- 0 9 * 7-9 1-5 date + '%T' >> /file    