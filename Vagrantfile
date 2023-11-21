Vagrant.configure("2") do |config|

  config.vm.box = "gusztavvargadr/ubuntu-server"   # 1 - Box (imagem base) a ser usada por todas as vms

  config.vm.define "vm1" do |vm1|

    vm1.vm.network "forwarded_port", guest: 67, host: 67 # 2  - Configuração de rede
    vm1.vm.network "private_network", ip: "192.168.56.10"
    vm1.vm.synced_folder "/var/www/html", "/var/www/html" #3 - Pasta Compartilhada
   
    vm1.vm.provision "shell", inline: <<-SHELL
      #ip route add default via 192.168.56.12
      export DEBIAN_FRONTEND=noninteractive
      apt update
      apt install -y docker.io
      #docker build -t gns3/dhcp .
      #docker run -dit --name gns3/dhcp
      #docker push gns3/dhcp
    SHELL
  end

  config.vm.define "vm1" do |vm2|

    vm1.vm.network "forwarded_port", guest: 67, host: 67 # 2  - Configuração de rede
    vm1.vm.network "private_network", ip: "192.168.56.10"
    vm1.vm.synced_folder "/var/www/html", "/var/www/html" #3 - Pasta Compartilhada
   
    vm1.vm.provision "shell", inline: <<-SHELL
      #ip route add default via 192.168.56.12
      export DEBIAN_FRONTEND=noninteractive
      apt update
      apt install -y docker.io
    SHELL
  end
end