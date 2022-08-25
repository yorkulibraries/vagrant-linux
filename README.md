# vagrant-linux
Setup a box to test [linux_playbooks] (https://github.com/yorkulibraries/linux_playbooks.git)

You can also use this to start a Vagrant box that is configured similar to the way our servers are configured.

## Installation
```
git clone https://github.com/yorkulibraries/vagrant-linux.git
cd vagrant-linux
git clone https://github.com/yorkulibraries/linux_playbooks.git
ansible-galaxy install -r linux_playbooks/requirements.yml 
```

### Vagrant up
```
vagrant up
```

### Run a playbook
```
ansible-playbook linux_playbooks/setup_new_server.yml
```

If a playbook applies to a group, then add vagrant-linux into that group within the **inventory** file
