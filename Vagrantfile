Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu-20.04"
  config.vm.box_url = "https://storage.yandexcloud.net/vbox/vbox_ubuntu-20.04"
  config.vm.box_check_update = false

  config.vm.provider "virtualbox" do |vb|
    vb.name = "ubuntu"  
    vb.cpus = 2
    vb.memory = "2048"
    vb.gui = false
  end
  
  config.vm.network "forwarded_port", guest: 3000, host: 3000

  config.vm.provision "file", source: "./ansible", destination: "/home/vagrant/"

  config.vm.provision "shell", inline: <<-SHELL
    sudo apt-get update
    sudo apt-get install ansible -y
    sudo timedatectl set-timezone "Europe/Moscow" 
    cd /home/vagrant/ansible  
    ansible-playbook ./playbooks/main.yml -i ./inventory/hosts.ini
  SHELL

end