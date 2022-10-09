# ansible-pihole

Ansible playbook for installing and managing a pihole + pivpn

## Setup Ansible User

If we have a fresh install, we first need to set up our ansible user that is going to execute our ansible playbook

SSH into pihole

```bash
ssh pi@pihole
```

Add __ansible__ user

```bash
sudo adduser --quiet --shell /bin/bash -ingroup sudo ansible
```

Copy across public key for our ansible user

``` bash
ssh-copy-id -f -i ~/.ssh/ansible.pub ansible@pihole
```

## Confirm pihole.ini

```bash
ansible pihole -m ping -v --ask-become-pass
```

#### Reference

* [44 Ansible Best Practices to Follow](https://spacelift.io/blog/ansible-best-practices)
* [Github Eideen/ansible-pihole](https://github.com/Eideen/ansible-pihole)
* [zfuller/pihole](https://github.com/zfuller/pihole)