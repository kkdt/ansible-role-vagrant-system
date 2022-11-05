# Ansile Role: vagrant-system

> Configure a system for Vagrant.

## Requirements

None

## Role Variables

The default Ansible variables are in [defaults](defaults/main.yml). The default password is `vagrant` unless otherwise specified.

<details>
 <summary>Generate password</summary>

 ```shell
 openssl passwd -1 <password>
 ```
</details>

```yaml
vagrant_username: The 'vagrant' user
vagrant_group: The 'vagrant' group
vagrant_password: The quoted password
```

## Dependencies

1. Ansible [community.general](https://galaxy.ansible.com/community/general)

## Ansible Galaxy

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

## Test

1. Install requirements
    ```shell
    ansible-galaxy install -r tests/requirements.yml --force
    ```
1. Execute test playbook
    ```shell
    ansible-playbook tests/test.yml
    ```