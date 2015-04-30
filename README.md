# Solr #

This repository contains a Vagrantfile and playbook for installing solr (and Java 8)

Installs solr instances as services

### Notes ###

* Arbitrarily used Ubuntu 32-bit (hashicorp/precise32)
* Vagrantfile currently includes port forwarding (guest: 8983 to host: 8983)
* Arbitrarily creates 3 nodes with 1 core each
