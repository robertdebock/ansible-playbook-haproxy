# Ansible Playbook HAProxy

A minimal playbook to provision multiple machines.

## Overview

```text
            +--- frontend-01 ---+
            | - haproxy         |
            +-------------------+
                     / \
                    /   \
                   V     V
+--- backend-01 ----+   +--- backend-02 ----+
| - httpd           |   | - httpd           |
+-------------------+   +-------------------+
```

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
