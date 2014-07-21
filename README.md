twofishes-vagrant
=====================================

## Requirements

- GIT, Java, ... the basic stuff
- VirtualBox https://www.virtualbox.org/
- Vagrant http://www.vagrantup.com/ 
- Ansible http://docs.ansible.com/

## Getting Started
    
    git clone git@github.com:torbjokv/twofishes-vagrant.git && cd twofishes-vagrant && vagrant up

This takes time. Grab a coffee - or two!

    Enter http://localhost:8882/ in your browser

    To do a reverse location query, do something like 
    http://localhost:8881/?ll=63.4350351,10.4096522&responseIncludes=PARENTS&maxInterpretations=1&lang=no


## To deploy in digital ocean

- Modify provisioning/groups_vars/all `twofishesservers_targets` to your server name
- Export your digital ocean api credentials (api version 1) to the console, or add them to your bash profile.
- Run: 
    ansible-playbook provisioning/digitalocean.yml
- Enter http://[your server]:8082/ in your browser

## Thanks to

- https://github.com/foursquare/twofishes
- https://github.com/vrischmann/ansible-role-java
- https://github.com/mortik/ansible-mongodb-role
- https://github.com/ansible/ansible
- https://github.com/mitchellh/vagrant


## License

This project is released under the MIT license (see the LICENSE file).
