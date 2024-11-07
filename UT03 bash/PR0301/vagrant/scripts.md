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
    if [ -r $ruta ]
    then 
            echo "El archivo existe y tienes permisos de lectura."
    else 
            echo "El archivo no existe o no tienes permisos de lectura."
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
    while [ $(($n % 2)) -eq 0 ] 
        do
                echo "$n"
        done