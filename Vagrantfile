# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure(2) do |config|

  # Using the Ubuntu 12.04 LTS 32-bit box from
  # https://atlas.hashicorp.com/search.
  config.vm.box = "hashicorp/precise32"

  # Disable automatic box update checking. If you disable this, then
  # boxes will only be checked for updates when the user runs
  # `vagrant box outdated`. This is not recommended.
  # config.vm.box_check_update = false

  # Setting up port forwarding to directly align with solr's default
  # settings. Accessing "localhost:8983" will access port 8983 on 
  # the guest machine.
  config.vm.network :forwarded_port, host: 8983, guest: 8983

  # Setting up ansible as the provisioner.
  # Also setting up playbook.yml as the file that will contain the
  # desired tasks to run.
    config.vm.provision :ansible do |ansible|
        ansible.playbook = "playbook.yml"
    end
end
