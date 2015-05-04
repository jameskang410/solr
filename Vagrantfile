# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
# Currently set up to create 3 boxes with specific, private IP addresses

Vagrant.configure(2) do |config|

  config.vm.define "host1" do |host1|
    # Using the Ubuntu 12.04 LTS 32-bit box from
    # https://atlas.hashicorp.com/search.
    host1.vm.box = "hashicorp/precise32"
    # Setting up a private IP address
    host1.vm.network "private_network", ip: "10.0.0.0"
    # Setting up port forwarding
    host1.vm.network :forwarded_port, host: 8983, guest: 8983
    # Setting up ansible as the provisioner.
    # Also setting up playbook.yml as the file that will contain the
    # desired tasks to run.
    host1.vm.provision :ansible do |ansible|
      ansible.playbook = "playbook.yml"
    end
  end

  config.vm.define "host2" do |host2|
    # Using the Ubuntu 12.04 LTS 32-bit box from
    # https://atlas.hashicorp.com/search.
    host2.vm.box = "hashicorp/precise32"
    # Setting up a private IP address - skipped 10.0.0.1 because it's 
    # usually reserved for routers
    host2.vm.network "private_network", ip: "10.0.0.2"
    # Setting up port forwarding
    host2.vm.network :forwarded_port, host: 8984, guest: 8984
    # Setting up ansible as the provisioner.
    # Also setting up playbook.yml as the file that will contain the
    # desired tasks to run.
    host2.vm.provision :ansible do |ansible|
      ansible.playbook = "playbook.yml"
    end
  end

  config.vm.define "host3" do |host3|
    # Using the Ubuntu 12.04 LTS 32-bit box from
    # https://atlas.hashicorp.com/search.
    host3.vm.box = "hashicorp/precise32"
    # Setting up a private IP address
    host3.vm.network "private_network", ip: "10.0.0.3"
    # Setting up port forwarding to directly align with solr's default
    # settings. Accessing "localhost:8983" will access port 8983 on 
    # the guest machine.
    host3.vm.network :forwarded_port, host: 8985, guest: 8985
    # Setting up ansible as the provisioner.
    # Also setting up playbook.yml as the file that will contain the
    # desired tasks to run.
    host3.vm.provision :ansible do |ansible|
      ansible.playbook = "playbook.yml"
    end
  end
end
