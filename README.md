Role Name
=========

ansible-role_vagrant_user

The goal is to override the default vagrant credentials with your own values for security

Requirements
------------

If vagrant exists the settings are applied \
If vagrant user does not exists no settings are applied (so in a way vagrant user existence is not a requirement) \
Tested on RHEL9 and Debian10 and Ubuntu24

Role Variables
--------------

*vagrant_user*: vagrant # typically (or even always this is vagrant) \
*vagrant_pass*: my_password # as an example \
*vagrant_pass_hash*: typcally created with python3 -c "import crypt; print(crypt.crypt('my_password', crypt.mksalt(crypt.METHOD_SHA512)))" \
*vagrant_public_key*: # create the pub/priv pair with ssh-keygen \
*vagrant_private_key*: #

E.g. defined in group_vars/all.yml if its ok that all hosts have same vagrant credentials

Dependencies
------------

Only useful on VM that are deployed with vagrant

Example Playbook
----------------

    - hosts: servers
      roles:
         - arikkert.vagrant_user

with variables defined elsewhere

License
-------

BSD

Author Information
------------------

    ARK-ICT
    Andre Rikkert de Koe - ICT
