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

### Run a playbook to setup the new server
```
ansible-playbook linux_playbooks/setup_new_server.yml
```

If a playbook applies to a group, then add vagrant-linux into that group within the **inventory** file

For example, if you want to run linux_playbooks/install_php56.yml, you will add **vagrant-linux** under the [php56] group in **inventory** file. **NOTE: don't commit the inventory file back into this repo.**
```
[php56]
vagrant-linux
```

```
ansible-playbook linux_playbooks/install_php56.yml
```
