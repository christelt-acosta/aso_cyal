EJERCICIO 1:
    #!/bin/bash
    read -p "Dime un número: " num
    if [ $(($num % 2 )) -eq 0 ]
    then
        echo "Es par"
    else 
        echo "Es impar"
    fi 

EJERCICIO 2:
    #!/bin/bash
    read -p "Dime la ruta de un archivo: " ruta
    if [ -e $ruta ] 
    then
        if [ -r $ruta ]
        then 
                echo "El archivo existe y tienes permisos de lectura."
        else 
                echo "El archivo existe y no tienes permisos de lectura."
        fi
    else
        echo "El archivo no existe"
    fi

EJERCICIO 3:
    #!/bin/bash
    echo "Dime un numero: "
    read a
    echo "Dime otro numero: "
    read b
    if [ $a -eq $b ]
    then
            echo "El número $a es igual que $b."
    else
            if [ $a -gt $b ]
            then 
                    echo "El número $a es mayor que $b."
            else 
                    echo "El número $a es menor que $b."
            fi
    fi

EJERCICIO 4:
    #!/bin/bash
    pass="1234"
    read -p "Introduce la contraseña: " contra
    if [ $contra == $pass ]
    then
        echo "Contraseña correcta."
    else
        echo "Contraseña incorrecta."
    fi

EJERCICIO 5:
#!/bin/bash
read -p "Dime la ruta del directorio: " directorio

if [ -d $directorio ] then
    if [ -w $directorio ]
	 then
        	echo "El directorio $directorio existe y tiene permisos de escritura."
    else
        echo "El directorio $directorio existe, y no tiene permisos de escritura."
    fi
else
    echo "El directorio $directorio no existe. Se creará el directorio..."
    mkdir $directorio
    echo "Directorio $directorio creado con éxito."
fi

EJERCICIO 6:
    #!/bin/bash
    if [ $(whoami) = "root" ]
    then
       echo "Eres root."
    else
       echo "No eres root."
    fi

EJERCICIO 7:
        #!/bin/bash
read "Dime una nota: " nota
if [ $nota -ge 5 ]
then
    echo "Aprobado"
else
    echo "Suspenso"
fi


EJERCICIO 8:
#!/bin/bash
espaciolibre=$(df / | grep / | awk '{ print $5 }'| sed 's/%//g')
if [ $espaciolibre -lt 10 ] 
then
    echo "Advertencia: El espacio libre en el disco es inferior al 10%."
else
    echo "Espacio libre en disco: $espaciolibre%"
fi

EJERCICIO 9: 
#!/bin/bash
echo "Seleccione una opción:"
echo "1. Mostrar fecha"
echo "2. Ver archivos en el directorio actual"
echo "3. Salir"
read opcion
if [ $opcion -eq 1 ]
then
    echo "La fecha es: $(date)"
elif [ $opcion -eq 2 ]
then
    echo "Los archivos de este directorio son:"
    ls
elif [ $opcion -eq 3 ]
then
    echo "Saliendo..."
else
    echo "Opción no válida. Inténtelo de nuevo"
fi

EJERCICIO 10:
#!/bin/bash
read -p "Dime tu edad: " edad
if [ $edad -lt 18 ]
then
    echo "Eres menor de edad."
elif [ $edad -ge 18 ] && [ $edad -le 65 ]
then
    echo "Eres adulto."
else
    echo "Eres mayor de edad."
fi

 EJERCICIO 11:
 #!/bin/bash
read -p "Dame el nombre de un archivo: " file
if [ -e $file ]
then
    numlineas=$(wc -l < $file)
    echo "El archivo $file tiene $numlineas líneas."
else
    echo "El archivo '$file' no existe."
fi
