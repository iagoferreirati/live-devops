Vagrant.configure("2") do |config|
    config.vm.box = "ubuntu/focal64"
  
    config.vm.network "public_network", ip: "192.168.1.56"
    config.vm.synced_folder "./ansible/", "/tmp/ansible"
  
    config.vm.provision "shell", inline: <<-SHELL
      sudo apt update
      sudo apt -y install ansible
      sudo ansible-playbook /tmp/ansible/playbook.yml
  
      SHELL
    
    config.vm.provider "virtualbox" do |v|
      v.memory = 1024
      v.cpus = 2
    end
  end 