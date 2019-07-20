home_server_dns_coredns
=========

A simple role to install and configure coredns using a pre-compiled binary.

Requirements
------------

NA

Role Variables
--------------

```
Variable                                Level                 Description

home_server_dns_coredns_version         Default               CoreDNS Version
home_server_dns_coredns_port            Default               CoreDNS Port
home_server_dns_coredns_server_name     Default               DNS Server Name
home_server_dns_coredns_admin_email     Default               DNS Server Admin Email
home_server_dns_coredns_zones           Default               DNS Zone (Forward and Reverse)
```

Dependencies
------------

NA

Example Playbook
----------------

```
---
- hosts: home_server
  become: yes
  roles:
    - role: home_server_dns_coredns
      vars:
        home_server_dns_coredns_version: 1.5.2
        home_server_dns_coredns_port: 53
        home_server_dns_coredns_server_name: devserver.local
        home_server_dns_coredns_admin_email: admin.email.com
        home_server_dns_coredns_zones:
          - name: example.local
            reverse_zone: 168.192.in-addr.arpa
            a_records:
              - name: subdomain1
                ip: 192.168.1.111
              - name: subdomain2
                ip: 192.168.1.121
```

License
-------

BSD

Author Information
------------------

```
Petros Petrou
ppetrou@gmail.com
```
