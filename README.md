Role Name
=========

apache

[![Build Status](https://travis-ci.org/cmihai-ansible/apache.svg?branch=master)](https://travis-ci.org/cmihai-ansible/apache)

Ansible galaxy:
---------------

[https://galaxy.ansible.com/devopstoolbox.apache](https://galaxy.ansible.com/devopstoolbox.apache)

```bash
ansible-galaxy install devopstoolbox.apache
```

Requirements
------------

- For RHEL, a Red Hat subscription or functional local repository.

Role Variables
--------------

```
apache_enable_service: true
apache_copy_templates: true
apache_firewall_configure: true
apache_firewall_rules:
  - service: http
  - service: https
```

Dependencies
------------

- For Red Hat, subscription-manager.

Example Playbook
----------------

```yaml
---
- name: Install apache on localhost
  hosts:
    - localhost
  connection: local

  tasks:
    - name: apache is configured
      import_role:
        name: devopstoolbox.apache
      vars:
        apache_enable_service: true
        apache_copy_templates: true
        apache_firewall_configure: true
        apache_firewall_rules:
          - service: http
          - service: https
      tags: apache
```

License
-------

MIT

Author Information
------------------

- [Mihai Criveti](https://www.linkedin.com/in/devopstoolbox.)
