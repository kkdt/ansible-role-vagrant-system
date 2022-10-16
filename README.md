# Ansile Role: vagrant-system

> Configure a system for Vagrant.

## Requirements

None

## Role Variables

The default Ansible variables are in [defaults](defaults/main.yml). To generate the password, execute the following command.
The default passowrd is `vagrant` unless otherwise specified.

```shell
openssl passwd -1 <password>
```

```yaml
vagrant_username: The 'vagrant' user
vagrant_group: The 'vagrant' group
vagrant_password: The quoted password
```

## Dependencies

1. Ansible [community.general](https://galaxy.ansible.com/community/general)

## Ansible Galaxy 'requirements.yml' Configurations


```yaml
# Git/HTTPS
- name: vagrant-system
  src: git+https://github.com/kkdt/ansible-role-vagrant-system.git
  scm: git
  version: master

# Git/SSH
- name: vagrant-system
  src: git+ssh://git@github.com:kkdt/ansible-role-vagrant-system.git
  scm: git
  version: master

# Git/File
- name: vagrant-system
  src: git+file:///home/vagrant/ansible-role-vagrant-system
  scm: git
  version: master

```

```shell
ansible-galaxy role install --role-file requirements.yml --roles-path ~/.ansible/roles --force -vvv
```

### Playbook

```yaml
- hosts: localhosst
  connection: local
  roles:
    - role: vagrant-system
      vars:
        vagrant_userame: vagrant
        vagrant_group: vagrant
        vagrant_password: "$1$qgMxd1Lc$9ibeJNVeLNHgEiebUUftP."
```