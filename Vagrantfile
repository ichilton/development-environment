# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.box = "debian-8.2"

  # Forward ports to VM:
  # config.vm.network "forwarded_port", guest: 80, host: 8080

  # Provider specific config:
  config.vm.provider "virtualbox" do |vb|
     vb.memory = "1024"
  end

  # SSH agent forwarding:
  config.ssh.forward_agent = true

  # Provisioning:

  # config.vm.provision "shell", inline: <<-SHELL
  #   sudo apt-get update
  #   sudo apt-get install -y python
  # SHELL

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "provisioning/playbook.yaml"
  end
end
