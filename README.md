tc1-mf-vagrant
==============

Vagrant environment for topcoder member facing site.

## Prerequisites:
#### Virtualbox: https://www.virtualbox.org/wiki/Downloads
#### Vagrant: https://www.vagrantup.com/downloads

## Installation:
* Clone this repo
* Inside the folder repo, run the following commands: 
(Please note, the 'vagrant up' command is a 1GB download)

'''
Note if you are on a mac you need to intall osxfuse.  If you are using brew, here is the command: brew install Caskroom/cask/osxfuse
'''

```
vagrant plugin install vagrant-sshfs
vagrant up --provider=virtualbox #to bring up the VM
vagrant ssh #to ssh to the VM
```

* Home directory on vm will be mapped to your ~/tc-env on host by default, so ~/tc-env/tc-site will have the code for the site in it
* Set /etc/hosts file to include:
local.topcoder.com 192.168.33.10
* Visit http://local.topcoder.com
* Make sure to do a 'git pull' inside the tc-site folder before you get started
* The default login/pass for wp-admin is: tcdev/tcdev, no caching is on by default but some js/css changes require you to [Update JS/CSS Registry](http://dev1.topcoder.com/wp-admin/themes.php?page=options.php)
