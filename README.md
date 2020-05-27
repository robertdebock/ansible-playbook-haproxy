# Ansible Playbook HAProxy

A minimal playbook to provision multiple machines.

## Setup

```bash
ansible-galaxy install -r roles/requirements.yml
```

## Installing

```bash
ansible-playbook playbook.yml
```

## Testing

Now check the IP of a frontend instance using `vagrant ssh-config` and point your brower to that IP using `https://`.