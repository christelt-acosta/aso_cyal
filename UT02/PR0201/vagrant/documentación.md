
```
1.-

    1.
        En dir1, el propietario (root) tiene todos los permisos, el grupo del usuario propietario solo tiene permisos de lectura y ejecución y los demás solo tienen permisos de lectura y ejecución.
        En dir2 pasa lo mismo que en dir1.
    2.
        sudo chmod a-w dir2.
    3.
        sudo chmod 111 dir2.
    4.
        Ahora todos tienen los mismos permisos, de ejecución.
    5.
        cd dir2. Después, sudo mkdir dir21.
    6.
        sudo chmod 311 dir2.

2.-

a)
notación simbólica:
--> rwxrwxr-x: sudo chmod a+x fichero, sudo chmod g+w fichero
--> rwxr--r--: sudo chmod u+x fichero
--> r--r-----: sudo chmod o-r fichero, sudo chmod u-w fichero
--> rwxr-xr-x: sudo chmod a+x fichero
--> r-x--x--x: sudo chmod a+x fichero, sudo chmod u-w fichero, sudo chmod u-w fichero
--> -w-r----x: sudo chmod uo-r fichero, sudo chmod o+x fichero
--> -----xrwx: sudo chmod o+wx fichero, sudo chmod g+x fichero, sudo chmod ug-rw fichero
--> r---w---x: sudo chmod u-w fichero, sudo chmod go-r fichero, sudo chmod g+w fichero, sudo chmod o+x fichero
--> -w-------: sudo a-r fichero
--> rw-r-----: sudo chmod o-r fichero
--> rwx--x--x: sudo chmod a+x fichero, sudo chmod go-r fichero
b)
--> rwxrwxrwx: sudo chmod 777 fichero 
--> --x--x--x: sudo chmod 111 fichero
--> r---w---x: sudo chmod 421 fichero
--> -w-------: sudo chmod 200 fichero
--> rw-r-----: sudo chmod 640 fichero
--> rwx--x--x: sudo chmod 711 fichero
--> rwxr-xr-x: sudo chmod 755 fichero
--> r-x--x--x: sudo chmod 511 fichero
--> -w-r----x: sudo chmod 241 fichero
--> -----xrwx: sudo chmod 017 fichero

3.-

1) sudo addgroup asir, sudo adduser cyal1, sudo adduser cyal2, sudo usermod -G asir cyal1, sudo usermod -G cyal2.
2) sudo mkdir compartido, sudo chown :asir compartido.
3) sudo chmod 770 compartido.
4) sudo chmod g+s compartido, ls -l y tiene que salir rws en los permisos de
   grupo.
5) su cyal1, cd compartido, echo prueba > fichero1, ls - l me sale 664.
6) su cyal2, cd /compartido, nano fichero1, sí puedo acceder al fichero y también modificarlo.
7) Las ventajas son que no es necesario darle permisos a todos y que es algo más sencillo que darle permisos a cada usuario. Si no se aciva habría que darle permisos a cada usuario, dificultaría el trabajo.
8) sudo rm compartido -r, sudo deluser cyal1, sudo deluser cyal2.

4.-

1) sudo mkdir compartido, sudo chmod 777 compartido.
2) sudo adduser cyal1, sudo adduser cyal2.
3) cd compartido, su cyal1, echo prueba > fichero1, su cyal2, rm fichero1, se borró el archivo.
4)  sudo chmod +t compartido, ls -l, tiene que salir una t al final de los permisos.
5) su cyal1, echo hola>prueba, su cyal2, rm prueba, no se puede borrar el fichero.
6) Sticky bit te permite crear archivos y que los demas usuarios puedan leerlos pero no pueden borrarlos o modificarlos.
Para eliminar algún fichero tendría que ser propietario del fichero.
```


