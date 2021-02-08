Ansible Nextcloud Exporter
=========

This role installs nextcloud-exporter which is developed by Robert Jacob and can be found here: https://github.com/xperimental/nextcloud-exporter.  
The exporter will be run as systemd service with it's own user and Group.
The default is listening on 127.0.0.1:9205.

Requirements
------------

 - Ansible >= 2.9, may work with other versions, but no guarantee
 - The role is currently only tested with CentOS and RHEL 8, but as it contains nothing special it should work on nearly every other distribution using systemd

Role Variables
--------------

All variables can be found at `defaults/main.yml`.  
The only required variables are the following:

    # URL of your nextcloud instance
    nextcloud_exporter_nc_url: "https://cloud.example.com"
    # Username of an admin account
    nextcloud_exporter_nc_username: "admin"
    # password of this account (can also be an app password)
    nextcloud_exporter_nc_password: "password"

For better understanding of the configuration, check out the nextcloud-exporter repository of Robert Jacob:  
https://github.com/xperimental/nextcloud-exporter

Dependencies
------------

- bzip2 installed on the remote system

Example Playbook
----------------



    - hosts: nextcloud
      roles:
         - { role: kornkalle.ansible_nextcloud_exporter }
      vars:
        nextcloud_exporter_nc_url: "https://cloud.example.com"
        nextcloud_exporter_nc_username: "admin"
        nextcloud_exporter_nc_password: "password"

License
-------

MIT

Author Information
------------------

Nils Berg

-   nils.berg [at] helmholtz-berlin.de
-   n.berg [at] backslashseven.de
