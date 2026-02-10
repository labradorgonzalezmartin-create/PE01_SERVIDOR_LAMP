Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/focal64"
  config.vm.hostname = "lamp-server"

  config.vm.network "private_network", ip: "192.168.56.100"
  config.vm.network "forwarded_port", guest: 80, host: 8080

  config.vm.provider "virtualbox" do |vb|
    vb.name = "LAMP-Server"
    vb.memory = "2048"
    vb.cpus = 2
  end

  config.vm.synced_folder "./www", "/var/www/html", owner: "www-data", group: "www-data"

  # Scripts de provisioning organizados [cite: 82]
  config.vm.provision "shell", path: "scripts/install-apache.sh"
  config.vm.provision "shell", path: "scripts/install-mysql.sh"
  config.vm.provision "shell", path: "scripts/install-php.sh"
end