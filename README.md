tc1-mf-vagrant
==============

Vagrant environment for topcoder member facing site.

## Prerequisites:
#### Virtualbox: https://www.virtualbox.org/wiki/Downloads
#### Vagrant: https://www.vagrantup.com/downloads
#### On MacOS, osxfuse is required: http://osxfuse.github.io/ or brew install sshfs

## Installation:
* Clone this repo
* Inside the folder repo, run the following commands: 
(Please note, the 'vagrant up' command is a 1GB download)

```
vagrant plugin install vagrant-sshfs
vagrant up --provider=virtualbox #to bring up the VM
vagrant ssh #to ssh to the VM
```

* Home directory on vm will be mapped to your ~/tc-env on host by default, so ~/tc-env/tc-site will have the code for the site in it
* Set /etc/hosts file to include:
```
192.168.33.10 local.topcoder.com
192.168.33.10 local.topcoder-dev.com
192.168.33.10 local.topcoder-qa.com
```
* Make sure to do a 'git pull' inside the tc-site folder before you get started
* Run 'grunt dev' to build/watch the src folder. This will build the project and configure your local instance against the production database, so please use caution. To use the dev or qa databases, run src/conf/debug-local-dev.sh or src/conf/debug-local-dev.sh
* The site will be available from any of the above hostnames, but you will want to test using the domain that matches the database instance you have built for to avoid cookie conflicts, etc.
* The default login/pass for wp-admin is: tcdev/tcdev, no caching is on by default but some js/css changes require you to [Update JS/CSS Registry](http://dev1.topcoder.com/wp-admin/themes.php?page=options.php)
