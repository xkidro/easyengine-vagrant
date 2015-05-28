# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"


Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  config.vm.box = "ubuntu/trusty64"

  config.vm.provider "virtualbox" do |v|
  
     v.name = "ubuntu-trusty64"

  end

  config.vm.network "private_network", ip: "192.168.33.10"

  config.vm.hostname = "work.local"

  config.vm.provision "shell", path: "easyengine.sh"

  config.vm.provision "shell", inline: "sudo ee stack restart", run: "always"

  config.vm.synced_folder "logs/", "/var/log/ee", owner: "root", group: "root"

  config.vm.synced_folder "www/", "/var/www", owner: "www-data", group: "www-data"

end