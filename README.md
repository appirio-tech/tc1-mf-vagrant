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

* Home directory on vagrant machine will be mapped to your ~/tc-env on host machine by default, so ~/tc-env/tc-site will have the code for the site in it
* Set /etc/hosts file on host machine to include:
```
192.168.33.10 local.topcoder.com
192.168.33.10 local.topcoder-dev.com
192.168.33.10 local.topcoder-qa.com
```
* Make sure to do a 'git pull' inside the tc-site folder before you get started
* Run 'grunt dev' to build/watch the src folder. This will build the project and configure your local instance against the production database, so please use caution. To use the dev or qa databases, run src/conf/debug-local-dev.sh or src/conf/debug-local-dev.sh
  * Please not on MacOS if you run grunt dev from your ssh mapped folder, the fuse driver does not always play nice, so it is     best to run this from the vagrant machine via vagrant ssh and use the mapped folder just for code modifications.
* The site will be available from any of the above hostnames, but you will want to test using the domain that matches the database instance you have built for to avoid cookie conflicts, etc.
* If you are using the wordpress side:
  * The default login/pass for wp-admin is: tcdev/tcdev, no caching is on by default but some js/css changes require you to [Update JS/CSS Registry](http://dev1.topcoder.com/wp-admin/themes.php?page=options.php)
  * You will need to keep wp-config.php up to date with which backend you are using, for instance if you ran sr/conf/debug-local-dev.sh, you would need:
 
    ```
    Define('WP_SITEURL','http://local.topcoder-dev.com');
    Define('WP_HOME','http://local.topcoder-dev.com');
    ```
