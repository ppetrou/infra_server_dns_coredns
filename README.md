infra_server_dns_coredns
=========

A simple role to install and configure coredns using a pre-compiled binary.

Requirements
------------

* dnspython (python library, http://www.dnspython.org/) installed in the ansible controller


Role Variables
--------------

```
Variable                                 Level                 Description

infra_server_dns_coredns_version         Default               CoreDNS Version
infra_server_dns_coredns_port            Default               CoreDNS Port
infra_server_dns_coredns_server_name     Default               DNS Server Name
infra_server_dns_coredns_admin_email     Default               DNS Server Admin Email
infra_server_dns_coredns_zones           Default               DNS Zone (Forward and Reverse)
infra_server_dns_coredns_ip              Default               CoreDNS Listen IP
infra_server_dns_coredns_run_assertions  Default               Flag whether to run dig assertions
```

Dependencies
------------

NA

Example Playbook
----------------

```
---
- hosts: dns_server
  become: yes
  roles:
    - role: infra_server_dns_coredns
      vars:
        infra_server_dns_coredns_version: 1.5.2
        infra_server_dns_coredns_port: 53
        infra_server_dns_coredns_server_name: devserver.local
        infra_server_dns_coredns_admin_email: admin.email.com
        infra_server_dns_coredns_ip: 192.168.122.55
        infra_server_dns_coredns_zones:
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

Apache 2.0

Author Information
------------------

```
Petros Petrou
ppetrou@gmail.com
```
