# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.box = "debian-8.2"

  # Forward ports to VM:
  # config.vm.network "forwarded_port", guest: 80, host: 8080

  # Use NFS for synced folders (faster)
  # config.vm.synced_folder ".", "/vagrant", type: "nfs"

  # Provider specific config:
  config.vm.provider "virtualbox" do |vb|
    vb.memory = "1024"

    # For NFS, Virtualbox neesds a private network:
    # config.vm.network :private_network, type: "dhcp"
  end

  # SSH agent forwarding:
  config.ssh.forward_agent = true


  # Provisioning

  # Ansible needs python installed
  # i've built it into my basebox though
  # config.vm.provision "shell", inline: <<-SHELL
  #   sudo apt-get update
  #   sudo apt-get install -y python
  # SHELL

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "provisioning/playbook.yaml"

    ansible.groups = {
      "ruby-dev" => ["default"],
      "go-dev" => ["default"],
      "ansible" => ["default"],
      "database" => ["default"]
    }
  end
end

