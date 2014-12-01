tc1-mf-vagrant
==============

Vagrant environment for topcoder member facing site.

## Prerequisites:
#  Virtualbox: https://www.virtualbox.org/wiki/Downloads
#  Vagrant: https://www.vagrantup.com/downloads

## Installation:
1. Clone this repo
2. Inside the folder repo, run the following commands: 
(Please notethe first command is a 1GB download)

```
vagrant up --provider=virtualbox #to bring up the VM
vagrant ssh #to ssh to the VM
```

3. Set /etc/hosts file to include:
local.topcoder.com 192.168.33.10

4. Visit http://local.topcoder.com
