# Provisioning

Ansible playbook to provision my server.

## Requirements

- Linux machine
- Install [Ansible](https://www.ansible.com/) with `pip install ansible`
- Install `sshpass` with your package manager such as `apt` or `yum`

## Usage

```
git clone https://github.com/kingkingyyk/ServerProvisioning.git
cd ServerProvisioning
tee inventory.ini << END
[myserver]
<ip address>
END
ansible-playbook -i inventory.ini playbook.yaml --ask-become-pass -k -u <username>
```

## Extra Information

Tested with Ansible `10.6.0`.
