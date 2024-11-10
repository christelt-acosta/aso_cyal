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
#!/bin/bash
read - p "Dime el nombre del archivo:" file
extension="${file##*.}"
case "$extension" in
    txt)
        echo "El archivo es de tipo texto (.txt)"
        ;;
    zip|tar.gz)
        echo "El archivo es un archivo comprimido ($extension)"
        ;;
    *)
        echo "El archivo tiene una extensión diferente a .txt, .zip o .tar ."
        ;;
esac

EJERCICIO 3:
#!/bin/bash
echo "Selecciona una opción para convertir:"
echo "1. Metros a Kilómetros"
echo "2. Kilómetros a Metros"
echo "3. Pies a Metros"
echo "4. Metros a Pies"
read -p "Opción: " opcion
case $opcion in
    1)
        read -p "Introduce los metros: " metros
        km=$((metros / 1000))
        echo "$metros metros son $km kilómetros."
        ;;
    2)
        read -p "Introduce los kilómetros: " kilometros
        metros=$((kilometros * 1000))
        echo "$kilometros kilómetros son $metros metros."
        ;;
    3)
        read -p "Introduce los pies: " pies
        metros=$((pies * 3048 / 10000))
        echo "$pies pies son $metros metros."
        ;;
    4)
        read -p "Introduce los metros: " metros
        pies=$((metros * 328084 / 100000))
        echo "$metros metros son $pies pies."
        ;;
    *)
        echo "Opción no válida."
        ;;
esac

EJERCICIO 4:
#!/bin/bash
echo "Selecciona una opción:"
echo "1. Apagar el sistema"
echo "2. Reiniciar el sistema"
echo "3. Cerrar sesión"
read -p "Opción: " opcion
case $opcion in
    1)
        echo "Apagando el sistema..."
        sudo shutdown -h now
        ;;
    2)
        echo "Reiniciando el sistema..."
        sudo reboot
        ;;
    3)
        echo "Cerrando sesión..."
        pkill -KILL -u $USER
        ;;
    *)
        echo "Opción no válida."
        ;;
esac

EJERCICIO 5:
#!/bin/bash
read -p "Dime un número entre 1 y 7:" numero
case $numero in
    1) echo "Lunes" ;;
    2) echo "Martes" ;;
    3) echo "Miércoles" ;;
    4) echo "Jueves" ;;
    5) echo "Viernes" ;;
    6) echo "Sábado" ;;
    7) echo "Domingo" ;;
    *)
        echo "Número incorrecto."
        ;;
esac

EJERCICIO 6:
#!/bin/bash
read -p "Dime una calificación:" calificacion
case $calificacion in
    [9-10])
        echo "Sobresaliente"
        ;;
    [7-8])
        echo "Notable"
        ;;
    [5-6])
        echo "Aprobado"
        ;;
    [0-4])
        echo "Suspenso"
        ;;
    *)
	echo "Calificación inválida"
	;;
esac

EJERCICIO 7:
#!/bin/bash
read -p "Dime un número:" numero
case $numero in
    [0])
        echo "Cero"
        ;;
    [1-9]*)
        if [ $numero -gt 0 ]; then
            echo "Positivo"
        else
            echo "Negativo"
        fi
        ;;
    *)
        echo "Número no válido"
        ;;
esac

EJERCICIO 8:
#!/bin/bash
read -p "Introduce el nombre del servicio:" servicio
echo "Selecciona una opción:"
echo "1. Iniciar el servicio"
echo "2. Detener el servicio"
echo "3. Reiniciar el servicio"
read -p "Opción: " opcion
case $opcion in
    1)
        sudo systemctl start $servicio
        if [ $? -eq 0 ]; then
            echo "Servicio $servicio iniciado correctamente."
        else
            echo "Error al iniciar el servicio $servicio."
        fi
        ;;
    2)
        sudo systemctl stop $servicio
        if [ $? -eq 0 ]; then
            echo "Servicio $servicio detenido correctamente."
        else
            echo "Error al detener el servicio $servicio."
        fi
        ;;
    3)
        sudo systemctl restart $servicio
        if [ $? -eq 0 ]; then
            echo "Servicio $servicio reiniciado correctamente."
        else
            echo "Error al reiniciar el servicio $servicio."
        fi
        ;;
    *)
        echo "Opción no válida."
        ;;
esac

