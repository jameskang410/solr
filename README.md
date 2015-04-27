# Solr #

This repository contains a Vagrantfile and playbook for installing solr (and Java 8)

Still needs some work, but it's a start.

### Notes ###

* Arbitrarily used Ubuntu 32-bit (hashicorp/precise32)
* Arbitrarily saves solr in /etc/solr/
* Vagrantfile currently includes port forwarding (guest: 8983 to host: 8983)