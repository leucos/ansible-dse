Ansible DSE Role
================

This role installs [Datastax DSE](http://www.datastax.com/products/datastax-enterprise).

This role can install any of:
    - DSE (when `dse_install_dse` is True)
    - Opscenter (when `dse_install_opscenter` is True)
    - Datastax Agent (when `dse_opscenter_ip` is set)

Variables
---------

- `dse_install_opscenter`: set to true to install opscenter (default: False)
- `dse_install_dse`: set to true to install DSE (default: False)
- `dse_opscenter_ip`: opscenter IP for agent configuration (default: False)
- `dse_repository_login`: login for Datastax's DEB repository access (default: False, **mandatory**)
- `dse_repository_password`: login for Datastax's DEB repository access (default: False, **mandatory**)

Tests
-----

First, set your DSE repository credentials in `tests/ansible-dse/inventory/group_vars/all`.

Test can then be run using vagrant:

```
vagrant up
vagrant ssh -c specs
```

Note the VM is set to eat 4GB RAM.

Licence
-------

MIT