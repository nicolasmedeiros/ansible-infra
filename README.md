The aim of this project is to keep track of the different Roles for BLC infra.

v0.1: Solr, Java and Zookeper roles

# Requirements
Install Ansible:

[Official guide](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html)

OSX: [Via pip](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html#latest-releases-via-pip)

Windows: [Cygwin or Linux subsystem](https://geekflare.com/ansible-installation-windows/)


## Usage
_note: use private IP_

*Important*:  in your inventory file, specify an entry named `zk-host-XY` - where `XY` is a number (01, 02, etc) - for each zookeeper host

- Edit `http_host` and `solr_hosts` (use private ip) at: `/roles/nginx/defaults/main.yml` 
- Edit `zookeeper_hosts` at `/roles/zookeeper/defaults/main.yml` using the private IP for each zookeeper machine


requirements.yml specifies the requried roles for this project. To install them use:

`ansible-galaxy install -p roles -r requirements.yml -f` 


- [geerlingguy.solr](https://github.com/geerlingguy/ansible-role-solr)
Modify `defaults/main.yml` to set the version of Solr to be installed.

- [geerlingguy.java](https://github.com/geerlingguy/ansible-role-java) 
- [idealista.zookeeper_role](https://github.com/idealista/zookeeper_role)
- common: This playbook will execute a initial server setup for Ubuntu 18.04 systems, as explained in the guide on
[Initial Server Setup Guide for Ubuntu 18.04](https://www.digitalocean.com/community/tutorials/how-to-use-ansible-to-automate-initial-server-setup-on-ubuntu-18-04).
  
 
Please check the readme for each role for further details.


### running the playbook
Assuming that the inventory file is called `poc` 

`ansible-playbook site.yml -i poc -u root`

Limit the application of the playbook to one host:
`ansible-playbook site.yml -i poc -u root --limit solr-host-01`

  or to a group of hosts:
  
  `ansible-playbook site.yml -i poc -u root --limit solr_servers`

### upload.yml
Uploads files from localhost to remote server. Usage:
`ansible-playbook upload.yml -i poc -u root`
