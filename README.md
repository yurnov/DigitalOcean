Lerning to use Digital Ocean in Ansible
=========

Short Ansible playbook and roles to create droplet in DigitalOcean and work with them

Requirements
------------

Pre-requisites is DigitalOcean account (you may use my referal link https://m.do.co/c/ac7511463eef for registartion and you will get gets $50 in credit over 30 days) and API access token. If you haven't access token navigate to https://cloud.digitalocean.com/account/api/tokens and click to Generate New Token button, do not forget to allow write permitions. As well, you need to have ssh-key added you your DigitalOcean profile (you do not add key yet, go to https://cloud.digitalocean.com/account/security and do so). This kay will be used to access and provision your droplet. Latest added key will be used you you have added several.  

Variables
--------------

Default droplet size is `s-1vcpu-1gb`, default DigitalOcean region is `ams3` and default image is `ubuntu-18-04-x64`. This is defined in playbook/do_create_droplet/defaults/main.yml  

You may override this defaults by extravars, for example:

 `ansible-playbook digitalocean.yml -e "droplet_size=s-6vcpu-16gb droplet_region=sfo2 droplet_image=centos-7-x64 droplet_hostname=mybloghost"`

Please refer DigitalOcean documentation for supported values. As well, you may provide hostname of your droplet as var `droplet_hostname`, please look on example below

Dependencies
------------

Ansible (tested on version 2.8.3) and ansible dependencies, like python.  

Example Run
----------------

You should provide DigitalOcean API token with write permission to be able to use this playbook/roles, example of run:

 `ansible-playbook digitalocean.yml -e "do_api=c010187272c8a7b5bff5bfr5bdrced563bfrlbc4846539bdrv0985ca2b847cbda droplet_hostname=mytestproplet"`

*This is not valid key, you should use your own key instead! 
