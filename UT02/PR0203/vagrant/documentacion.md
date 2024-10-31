```
Para esta práctica en el Vagrantfile puse la dirección de red que también deben tener acceso mis compañeros.
Luego creé un usuario para cada uno, incluido uno para mi.
Después inicié sesión con mi usuario con su christelt, luego usé ssh-keygen -b 1024 para generar la clave para mi usuario.
Con scp .ssh/id_rsa.pub christelt@ip(de la otra máquina):/home/christelt pasé la contraseña a mi usuario en las máquinas de mis compaeñeros.
Luego me conecté a esas máquinas con ssh christelt@ip.
Ahora creo el directorio .ssh y muevo la clave a authorized_keys con mv id_rsa.pub .ssh/authorized_keys.
```