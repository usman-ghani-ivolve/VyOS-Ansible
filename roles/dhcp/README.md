DHCP
====

This role configure DHCP.

Requirements
------------

- Management Network configuration with done with cloud-init
- SSH service is enable and listening on Management IP.

Role Variables
--------------
**Add DHCP**
```
action
network_name
subnet
range
dhcp_start
dhcp_end
default_router
dns_server
lease
```
**Remove DHCP**
```
action
network_name
subnet
```
**Enable/Disable DHCP**
```
action
network_name
```
**Add/Remove DNS**
```
action
network_name
subnet
dns_server
```
**Add/Remove DHCP Range**
```
action
network_name
subnet
range
dhcp_start
dhcp_end
```

Dependencies
------------

None

Example Playbook
----------------
A reference playbook with required variables for this role.

    ---
    - hosts: vyos-2        
      roles:
        - role: dhcp
          vars:
            action: "add"
            network_name: "LAN"
            subnet: "192.168.0.0/24"
            range: "default_range"
            dhcp_start: "192.168.0.2"
            dhcp_end: "192.168.0.254"
            default_router: "192.168.0.1"
            dns_server: "8.8.8.8"
            lease: "86400"