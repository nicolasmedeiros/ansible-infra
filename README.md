The aim of this project is to keep track of the different Roles for BLC infra.

# Requirements
Install Ansible:
[Official guide](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html)

OSX: [Via pip](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html#latest-releases-via-pip)
Windows: [Cygwin or Linux subsystem](https://geekflare.com/ansible-installation-windows/)


## Usage
requirements.yml specifies the requried roles for this project. To install them use:

`ansible-galaxy install -p roles -r requirements.yml -f` 

- [geerlingguy.solr](https://github.com/geerlingguy/ansible-role-solr)
- [geerlingguy.java](https://github.com/geerlingguy/ansible-role-java) 
- [idealista.zookeeper_role](https://github.com/idealista/zookeeper_role)
- common: This playbook will execute a initial server setup for Ubuntu 18.04 systems, as explained in the guide on
[Initial Server Setup Guide for Ubuntu 18.04](https://www.digitalocean.com/community/tutorials/how-to-use-ansible-to-automate-initial-server-setup-on-ubuntu-18-04).
  


