# -*- mode: ruby -*-
# vi: set ft=ruby :

if Vagrant::Util::Platform.wsl?
  unless Vagrant.has_plugin?("virtualbox_WSL2")
    raise 'virtualbox_WSL2 is not installed, install with "vagrant plugin install virtualbox_WSL2"'
  end
end

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  # General VM configuration.
  config.vm.box = "geerlingguy/debian11"

  # Sync configuration.
  if Vagrant::Util::Platform.wsl?
    config.vm.synced_folder ".", "/vagrant", disabled: true
  end

  # Virtualbox VM configuration.
  config.vm.provider :virtualbox do |v|
    v.cpus = 1
    v.memory = 256
  end
end
