tc1-mf-vagrant
==============

Vagrant environment for topcoder member facing site.

## Prerequisites:
#### Virtualbox: https://www.virtualbox.org/wiki/Downloads
#### Vagrant: https://www.vagrantup.com/downloads

## Installation:
* Clone this repo
* Inside the folder repo, run the following commands: 
(Please note, the first command is a 1GB download)

```
vagrant up --provider=virtualbox #to bring up the VM
vagrant ssh #to ssh to the VM
```

* Set /etc/hosts file to include:
local.topcoder.com 192.168.33.10

* Visit http://local.topcoder.com
* Usually a good idea to do a 'git pull' inside the tc-site folder on the vagrant box
