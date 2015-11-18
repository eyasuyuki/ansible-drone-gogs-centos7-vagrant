# Requirements

- Ansible
- Vagrant

# Clone this repository

```
git clone git@github.com/eyasuyuki/ansible-drone-gogs-centos7-vagrant.git
```

# Initialize Vagrant box

```
cd ansible-drone-gogs-centos7-vagrant
vagrant box add centos7 https://github.com/CommanderK5/packer-centos-template/releases/download/0.7.1/vagrant-centos-7.1.box
vagrant up
```

# Test Ansible


```
ansible all -u vagrant -m shell -a "ps axu" -vvvv --private-key=.vagrant/machines/default/virtualbox/private_key
```

# Install Drone.io and Gogs

```
ansible-playbook setup.yml -vvvv --private-key=.vagrant/machines/default/virtualbox/private_key
```

# Test PostgreSQL

```
psql -U postgres --host 192.168.33.10 --port 5432
```

