ansible-openstack-cloud-launcher
================================

Requirements
------------

shade library needs to be installed, as that is required by the
OpenStack Ansible modules.

Role Variables
--------------

The role expects variables fed by ansible-playbook
on the CLI, e.g. 'ansible-playbook -i inventory play.yml -e "@resources.yml"'.
Please check resources.yml.sample on this repository for a full-blown example.


Dependencies
------------

None

Example playbook
----------------
```
  ---
  - hosts: localhost
    connection: local
    gather_facts: false
    roles:
      - { role: ansible-openstack-cloud-launcher }
```

License
-------

Apache

Author information
------------------

ansible-openstack-cloud-launcher is maintained by Ricardo Carrillo Cruz.
The best way to contact him is on #openstack-infra on freenode.
