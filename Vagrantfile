
Vagrant.configure("2") do |config|

  config.vm.box = "ubuntu/jammy64"
  config.vm.network "private_network", ip: "192.168.33.10" # IP estática
  config.vm.provider "virtualbox" do |vb|
    vb.memory = "512" # RAM
    vb.cpus = 1 # CPU
  end
  config.vm.synced_folder "C:/Users/robin/html/html", "/var/www/html"
  config.vm.provision "shell", inline: <<-SHELL
    sudo apt-get update
    sudo apt-get install -y apache2
    sudo systemctl enable apache2
    sudo systemctl start apache2
  SHELL
end
