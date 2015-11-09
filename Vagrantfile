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

  config.vm.provider "virtualbox" do |vb|
    # Use NFS for synced folders (faster):
    # config.vm.network :private_network, ip: "33.33.33.10"
    # config.vm.synced_folder ".", "/vagrant", type: "nfs"
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
