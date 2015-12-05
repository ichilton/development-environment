Local Vagrant Development Environment

Vagrantfile and Ansible provisioning for a Ruby & Go development environment.

Needs a Debian 8 base box.

Tested with Virtualbox, VMWare Fusion, libvirt

Example usage:

```
  mkdir -p vagrant/dev
  cd vagrant/dev
  git clone https://github.com/ichilton/development-environment.git provisioning
  ln -s provisioning/Vagrantfile
  vagrant up
```

TODO:
  - Pull out configurables into variables and ruby builds into loop
  - More complete documentation
  - Databases - MySQL, Postgres & client libraries

