# Práctica 2 - Entornos multimáquina

## Pasos que seguí
1. ** Verificar si tengo los boxes **
    - Necesito el box del Windows Server 2019 y el de un Windows 10, hay que buscarlo en Vagrant boxes.
2. ** Descargar los boxes **
    - Me descargué 'StefanScherer/windows_2019' para el Windows Server 2019 y 'scotch/box' para el Windows 10. Los descargué con el comando 'vagrant box add StefanScherer/windows_2019' y 'vagrant box add scotch/box'
3. ** Iniciar el vagrantfile**
    - Inicialicé el vagrantfile con el comando 'vagrant init', luego lo edité así:
    ```
        # -*- mode: ruby -*-
        # vi: set ft=ruby :

         Vagrant.configure("2") do |config|

            config.vm.define "win2019" do | w19|
                w19.vm.box = "StefanScherer/windows_2019"
                w19.vm.network "private_network", ip: "172.19.0.10" 
                w19.vm.provider "virtualbox" do |vb|
                    vb.name = "windows server 2019"
                    vb.memory = 4192
                    vb.cpus = 4
                    end
            end 

            config.vm.define "win10" do | w10|
                w10.vm.box = "gusztavvargadr/windows-10"
                w10.vm.network "private_network", ip: "172.19.0.11" 
                w10.vm.provider "virtualbox" do |vb|
                    vb.name = "windows 10"
                    vb.memory = 2048
                    vb.cpus = 2
                    end
            end 
        
        end
    ```
    4. ** Conectividad ** 
    -  Para que las máquinas estén conectadas entre sí y se vean con el anfitrión, hay que establecer 
     una red privada en cada una de las máquinas.
    5. ** Iniciar las máquinas virtuales **
    - Para iniciar las máquinas virtuales que hemos configurado usamos el comando 'vagrant up' y se levantarán las dos máquinas.
    6. ** Conectarse con vagrant **
    Me contecté con el comando 'vagrant ssh
    y el nombre de la máquina
    7. Hay que hacer ping entre mi anfitrion y las dos máquinas que instalamos
