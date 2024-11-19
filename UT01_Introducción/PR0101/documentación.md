# Práctica 1 - Introduccion a Vagrant

## Pasos que seguí

1. ** Descargar Vagrant **
2. ** Verificar la lista de boxes  **
    - Con el comando 'vagrant box list' se puede saber que boxes tengo descargadas. Como no tengo ninguna, tengo que ir a **Vagrant Boxes** a buscar el box que necesito, en este caso necesito el de Ubuntu Server 20.04. Elegí "peru/my_ubuntu-20.04-server-amd64".
3. ** Descargar el box **
    - Para descargar el box que elegimos se utiliza el comando 'vagrant box add peru/my_ubuntu-20.04-server-amd64', 
4. ** Crear Vagrantfile **
    - Ahora creamos la carpeta donde se guardará la máquina virtual
    luego, con el comando 'vagrant init -m' se creará el Vagrantfile. 
5. ** Configurar el Vagrant File **
    - Aquí está el ejemplo de mi Vagrantfile: 
    ```
        # -*- mode: ruby -*-
        # vi: set ft=ruby :

        Vagrant.configure("2") do |config|
        config.vm.box = "peru/my_ubuntu-20.04-server-amd64"
        config.vm.hostname = "servercyal"
        config.vm.synced_folder "./carpetadata", "/data", create=true
        config.vm.provider "virtualbox" do |vb|
            vb.name = "ubuntu server"
            vb.memory = 2048
            vb.cpus = 2
        end
        end
    ```
6. ** Iniciar la máquina **
    - Para levantar la máquina usaremos el comando 'vagrant up', es importante que estemos en la carpeta donde esta el Vagrantfile cuando ejecutamos este comando.
7. ** Ya está la máquina creada **
    

