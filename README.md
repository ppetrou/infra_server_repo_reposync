infra_server_repo_reposync
=========

A simple role to sync yum repos. The role will install httpd to serve the synced repos and store them at /var/www/html. Custom directories are not supported in this version.

Requirements
------------

* Access to the syncing repos from the target host. 
* A valid RHN subscription for Red Hat repos.

Releases
------------

|Branch|Status|Description| Date
|---	|---	|---	|---
|main|Unstable|Development Branch|Now
|1.0.0|Release|Release 1.0.0|16-08-2021


Role Variables
--------------

|Variable|Level|Type|Description
|---|---|---|---	
|repolist|Default|list(string)|The repolist to sync


Dependencies
------------

* ansible.posix collection - https://docs.ansible.com/ansible/latest/collections/ansible/posix/index.html

Example Playbook
----------------

```
---
- hosts: repo_server
  become: yes
  roles:
    - role: infra_server_repo_reposync
      vars:
        repolist:
          -  ansible-2.9-for-rhel-8-x86_64-rpms
          -  advanced-virt-for-rhel-8-x86_64-rpms 
          -  satellite-tools-6.5-for-rhel-8-x86_64-rpms
```

License
-------

Apache-2.0

Author Information
------------------

```
Petros Petrou
email: ppetrou@gmail.com
web: www.petrospetrou.co.uk
```

