===========================
ansible-role-cloud-launcher
===========================

Ansible role to launch multiple OpenStack Clouds resources

* License: Apache License, Version 2.0
* Documentation: https://ansible-role-cloud-launcher.readthedocs.org
* Source: https://git.openstack.org/cgit/openstack/ansible-role-cloud-launcher
* Bugs: https://bugs.launchpad.net/ansible-role-cloud-launcher

Description
-----------

ansible-role-cloud-launcher is an Ansible role that allows to launch
multiple OpenStack clouds resources.
Resources can be defined in a cloud by cloud basis or defined in a profile,
which may be reused by more than one cloud.

Requirements
------------

shade library needs to be installed, as that is required by the
OpenStack Ansible modules.

Role Variables
--------------

The role expects variables fed by ansible-playbook
on the CLI, for example: 

    ansible-playbook -i inventory play.yml -e "@resources.yml"

The role expects the resources variables file to have two dict variables,
*profiles* and *clouds*.

*profiles* contains a list of OpenStack resources definitions
that are meant to be reused by one or more clouds.

*clouds* contains a list of clouds the role will launch resources on. Each
cloud definition will have the OSCC cloud name, a list of profiles the cloud
will reuse and a list of resources specific to that cloud.

Please check resources.yml.sample on this repository for a full-blown example.


Dependencies
------------

None

Example playbook
----------------

.. code-block:: yaml

  ---
  - hosts: localhost
    connection: local
    gather_facts: false
    roles:
      - { role: ansible-role-cloud-launcher }
