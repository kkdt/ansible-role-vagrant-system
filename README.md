# Ansile Role: vagrant

> Configures a server for Vagrant.

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

Collections

1. Ansible [community.general](https://galaxy.ansible.com/community/general)

## Ansible Galaxy 'requirements.yml' Configurations


```yaml
# Git/HTTPS
- name: kkdt.vagrant
  src: git+https://github.com/kkdt/vagrant
  scm: git
  version: master

# Git/SSH
- name: kddt.vagrant
  src: git+ssh://git@github.com/kkdt/vagrant
  scm: git
  version: master

# Git/File
- name: kddt.vagrant
  src: git+file:///home/kkdt/vagrant
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
  vars:
    - vagrant_userame: vagrant
    - vagrant_group: vagrant
    - vagrant_password: "$1$9N3tAnJv$hPgSQo434gS8gZupEfAtx."
  roles:
    - kkdt.vagrant
```