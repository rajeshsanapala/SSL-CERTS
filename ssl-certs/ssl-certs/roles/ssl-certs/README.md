Role Name
=========

To Auto renew the ssl certificates on target server before expiry 

Requirements
------------

Ensure Ansible vault is copied with the content of ca, crt, privatekey files on local host.

Role Variables
--------------
vault/certs/certificate.yml
vars/main.yml

Dependencies
------------

Ansible vault with certificates

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

- name: Create or Replace expired SSL certificates
  hosts: localhost
  tasks:
    - include_role:
        name: ssl-certs
    - include_vars: vault/certs/certificate.yml

ansible-playbook -i inventory ssl-certs.yml -vvv -ask-vault-pass

License
-------

BSD

Author Information
------------------

Rajesh Sanapala
