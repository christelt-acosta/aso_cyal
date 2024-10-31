
```
Habilité el adaptador como Red solo anfitrión.
Luego en la máquina virtual hice un ip a para saber la ip de mi máquina virtual.
Busqué la dirección IP del adaptador de red en mi máquina anfitrión.
Desde mi máquina anfitrión hice un ping a mi máquina virtual.
Cambié el nombre con el comando sudo hostnamectl set-hostname cyal_server.
En mi máquina anfitrión agregué cyal_server como host en el archivo C:\Windows\System32\drivers\etc\hosts.
En mi máquina virtual creé el usuario con sudo adduser cyal_ssh.
Creé la clave con ssh-keygen
Luego copié la clave en el servidor:
ssh-copy-id cyal_ssh@cyal_server.
```