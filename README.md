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

The state of the used roles:

|Role name|GitHub Action|GitLab CI|Version|
|---------|-------------|---------|-------|
|[bootstrap](https://galaxy.ansible.com/robertdebock/bootstrap)|[![github](https://github.com/robertdebock/ansible-role-bootstrap/workflows/Ansible%20Molecule/badge.svg)](https://github.com/robertdebock/ansible-role-bootstrap/actions)|[![gitlab](https://gitlab.com/robertdebock/ansible-role-bootstrap/badges/master/pipeline.svg)](https://gitlab.com/robertdebock/ansible-role-bootstrap)|[![version](https://img.shields.io/github/commits-since/robertdebock/ansible-role-bootstrap/latest.svg)](https://github.com/robertdebock/ansible-role-bootstrap/releases)|
|[buildtools](https://galaxy.ansible.com/robertdebock/buildtools)|[![github](https://github.com/robertdebock/ansible-role-buildtools/workflows/Ansible%20Molecule/badge.svg)](https://github.com/robertdebock/ansible-role-buildtools/actions)|[![gitlab](https://gitlab.com/robertdebock/ansible-role-buildtools/badges/master/pipeline.svg)](https://gitlab.com/robertdebock/ansible-role-buildtools)|[![version](https://img.shields.io/github/commits-since/robertdebock/ansible-role-buildtools/latest.svg)](https://github.com/robertdebock/ansible-role-buildtools/releases)|
|[core_dependencies](https://galaxy.ansible.com/robertdebock/core_dependencies)|[![github](https://github.com/robertdebock/ansible-role-core_dependencies/workflows/Ansible%20Molecule/badge.svg)](https://github.com/robertdebock/ansible-role-core_dependencies/actions)|[![gitlab](https://gitlab.com/robertdebock/ansible-role-core_dependencies/badges/master/pipeline.svg)](https://gitlab.com/robertdebock/ansible-role-core_dependencies)|[![version](https://img.shields.io/github/commits-since/robertdebock/ansible-role-core_dependencies/latest.svg)](https://github.com/robertdebock/ansible-role-core_dependencies/releases)|
|[epel](https://galaxy.ansible.com/robertdebock/epel)|[![github](https://github.com/robertdebock/ansible-role-epel/workflows/Ansible%20Molecule/badge.svg)](https://github.com/robertdebock/ansible-role-epel/actions)|[![gitlab](https://gitlab.com/robertdebock/ansible-role-epel/badges/master/pipeline.svg)](https://gitlab.com/robertdebock/ansible-role-epel)|[![version](https://img.shields.io/github/commits-since/robertdebock/ansible-role-epel/latest.svg)](https://github.com/robertdebock/ansible-role-epel/releases)|
|[haproxy](https://galaxy.ansible.com/robertdebock/haproxy)|[![github](https://github.com/robertdebock/ansible-role-haproxy/workflows/Ansible%20Molecule/badge.svg)](https://github.com/robertdebock/ansible-role-haproxy/actions)|[![gitlab](https://gitlab.com/robertdebock/ansible-role-haproxy/badges/master/pipeline.svg)](https://gitlab.com/robertdebock/ansible-role-haproxy)|[![version](https://img.shields.io/github/commits-since/robertdebock/ansible-role-haproxy/latest.svg)](https://github.com/robertdebock/ansible-role-haproxy/releases)|
|[hostname](https://galaxy.ansible.com/robertdebock/hostname)|[![github](https://github.com/robertdebock/ansible-role-hostname/workflows/Ansible%20Molecule/badge.svg)](https://github.com/robertdebock/ansible-role-hostname/actions)|[![gitlab](https://gitlab.com/robertdebock/ansible-role-hostname/badges/master/pipeline.svg)](https://gitlab.com/robertdebock/ansible-role-hostname)|[![version](https://img.shields.io/github/commits-since/robertdebock/ansible-role-hostname/latest.svg)](https://github.com/robertdebock/ansible-role-hostname/releases)|
|[httpd](https://galaxy.ansible.com/robertdebock/httpd)|[![github](https://github.com/robertdebock/ansible-role-httpd/workflows/Ansible%20Molecule/badge.svg)](https://github.com/robertdebock/ansible-role-httpd/actions)|[![gitlab](https://gitlab.com/robertdebock/ansible-role-httpd/badges/master/pipeline.svg)](https://gitlab.com/robertdebock/ansible-role-httpd)|[![version](https://img.shields.io/github/commits-since/robertdebock/ansible-role-httpd/latest.svg)](https://github.com/robertdebock/ansible-role-httpd/releases)|
|[openssl](https://galaxy.ansible.com/robertdebock/openssl)|[![github](https://github.com/robertdebock/ansible-role-openssl/workflows/Ansible%20Molecule/badge.svg)](https://github.com/robertdebock/ansible-role-openssl/actions)|[![gitlab](https://gitlab.com/robertdebock/ansible-role-openssl/badges/master/pipeline.svg)](https://gitlab.com/robertdebock/ansible-role-openssl)|[![version](https://img.shields.io/github/commits-since/robertdebock/ansible-role-openssl/latest.svg)](https://github.com/robertdebock/ansible-role-openssl/releases)|
|[python_pip](https://galaxy.ansible.com/robertdebock/python_pip)|[![github](https://github.com/robertdebock/ansible-role-python_pip/workflows/Ansible%20Molecule/badge.svg)](https://github.com/robertdebock/ansible-role-python_pip/actions)|[![gitlab](https://gitlab.com/robertdebock/ansible-role-python_pip/badges/master/pipeline.svg)](https://gitlab.com/robertdebock/ansible-role-python_pip)|[![version](https://img.shields.io/github/commits-since/robertdebock/ansible-role-python_pip/latest.svg)](https://github.com/robertdebock/ansible-role-python_pip/releases)|


```bash
ansible-galaxy install -r roles/requirements.yml
```

## Installing

```bash
ansible-playbook playbook.yml
```

## Testing

Now check the IP of a frontend instance using `vagrant ssh-config` and point your brower to that IP using `https://`.
