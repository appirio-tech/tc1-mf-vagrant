tc1-mf-vagrant
==============

Vagrant environment for topcoder member facing site.

Tested with Virtualbox: https://www.virtualbox.org/wiki/Downloads, if you have no VM provider, please download and install that.

Install vagrant for your platform
https://www.vagrantup.com/downloads

Clone this repo

Inside the folder repo, run

vagrant up #to bring up the VM

vagrant ssh #to sh to the VM

code is in tc-site folder
Set /etc/hosts file to include:
local.topcoder.com 192.168.33.10

Visit http://local.topcoder.com
