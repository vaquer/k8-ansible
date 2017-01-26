# k8-ansible
Install Kubernetes using Ansible

Installation
==============
Dependencies:

[Vagrant](http://www.vagrantup.com)

[Virtualbox](http://www.virtualbox.org)

[Ansible](http://www.ansible.com)


How to run
==============

```shell
$ vagrant up
```
If something goes wrong:
```shell
$ vagrant reload

$ vagrant provision
```

Deploy to production
====================
Add your servers to the inventory /etc/ansible/hosts

```
[masterservers]
192.168.1.1

[nodeservers]
192.168.1.2
```

Execute:

```shell
$ ansible-playbook provisioning/site.yml
```
```
< DONE! >
        \   ^__^
         \  (oo)\_______
            (__)\       )\/\
                ||----w |
                ||     ||
```
