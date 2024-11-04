EJERCICIO 1:
    #!/bin/bash
    echo "Selecciona una operacion: 
            1) suma
            2) resta
            3) multiplicacion
            4) division "
    read op
    case $op in
            1)
            echo "Escribe el primer numero: "
            read a
            echo "Escribe el segundo numero: "
            read b
            echo "La suma de $a + $b es "$(($a+$b));;
            2)
            echo  "Escribe el primer numero: "
            read a
            echo "Escribe el segundo numero"
            read b
            echo "La resta de $a - $b es " $(($a-$b));;
            3)
            echo "Escribe el primer numero: "
            read a
            echo "Escribe el segundo numero: "
            read b
            echo "La multiplicacion de $a * $b es "$(($a*$b));;
            4)
            echo "Escribe el primer numero: "
            read a 
            echo "Escribe el segundo numero: "
            read b
            echo "La division de $a / $b es "$(($a/$b));;
            *)
            echo "Has introducido una opcion invalida";;

    esac

EJERCICIO 2:
