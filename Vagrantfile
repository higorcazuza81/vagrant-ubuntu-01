
Vagrant

Vagrant.configure("2") do |config|
  
   config.vm.box = "adavilag/ubuntu-server-22.04.1"
   config.vm.box_version = "1.1"
   
   config.vm.hostname = "ubuntu-server"
   config.vm.network "public_network", bridge: "wlp2s0"

  config.vm.provider "virtualbox" do |vb|
    vb.memory = "1024"
    vb.cpus = 1
    vb.name = "ubuntu-server-22.04"
  end

  config.vm.synced_folder "~/Documents/Vagrant/vagrant-ubuntu", "/vagrant-ubuntu"
end
