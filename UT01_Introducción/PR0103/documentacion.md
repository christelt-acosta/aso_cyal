Pasos realizados

1. Creación del Vagrantfile

Iniciamos el directorio del proyecto y creamos el Vagrantfile con la configuración deseada:

mkdir vagrant-webserver
cd vagrant-webserver
vagrant init

Luego, editamos el Vagrantfile para que contenga la siguiente configuración:
# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
    # Definir la máquina virtual
    config.vm.define "web_server" do |web|
        web.vm.box = "ubuntu/jammy64"
        web.vm.hostname = "web-iniciales"
        
        # Asignar recursos
        web.vm.provider "virtualbox" do |vb|
            vb.name = "Web server"
            vb.memory = 3072
            vb.cpus = 2
        end
        
        # Configuración de redes
        web.vm.network "private_network", ip: "172.16.0.10"
        web.vm.network "public_network", ip: "10.99.0.10"
        
        # Aprovisionamiento: Instalación de Apache y configuración del sitio web
        web.vm.provision "shell", inline: <<-SHELL
            sudo apt update
            sudo apt install -y apache2
            sudo systemctl enable apache2
            sudo systemctl start apache2
            
            # Creación del sitio web
            sudo mkdir -p /var/www/html/misitio
            echo '<!DOCTYPE html><html><head><title>Inicio</title></head><body><h1>Página de inicio</h1></body></html>' | sudo tee /var/www/html/misitio/index.html
            echo '<!DOCTYPE html><html><head><title>Nosotros</title></head><body><h1>Página sobre nosotros</h1></body></html>' | sudo tee /var/www/html/misitio/nosotros.html
            echo '<!DOCTYPE html><html><head><title>Contacto</title></head><body><h1>Página de contacto</h1></body></html>' | sudo tee /var/www/html/misitio/contacto.html
            
            # Copiar una imagen al sitio web
            sudo cp /var/www/html/index.html /var/www/html/misitio/imagen.jpg
            
            # Configuración de Apache
            sudo tee /etc/apache2/sites-available/misitio.conf <<EOF
            <VirtualHost *:80>
                DocumentRoot "/var/www/html/misitio"
                <Directory "/var/www/html/misitio">
                    Options Indexes FollowSymLinks
                    AllowOverride None
                    Require all granted
                </Directory>
            </VirtualHost>
            EOF
            
            sudo a2ensite misitio.conf
            sudo systemctl restart apache2
        SHELL
    end
end