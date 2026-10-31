# Provisioning

Ansible playbook to provision my server.

## Requirements

- A Linux Machine with `uv` (curl -LsSf https://astral.sh/uv/install.sh | sh)
- Install `sshpass` with your package manager such as `apt` or `yum`

## Usage

```
git clone https://github.com/kingkingyyk/ServerProvisioning.git
cd ServerProvisioning
uv init
uv add ansible
uv run ansible-galaxy collection install ansible.posix community.general
tee inventory.ini << END
[myserver]
<ip address>

[all:vars]
ansible_ssh_common_args='-o StrictHostKeyChecking=no'
ansible_become_exe='/usr/bin/sudo.ws'
END
ansible-playbook -i inventory.ini playbook.yaml --ask-become-pass -k -u <username>
```

## Extra Information

Tested with ansible-core `2.21.5` & Ubuntu `26.04`.
