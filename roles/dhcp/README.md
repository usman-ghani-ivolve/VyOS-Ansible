Role Name
=========

This role fetch router configuration.

Requirements
------------

- Management Network configuration with done with cloud-init
- SSH service is enable and listening on Management IP.

Role Variables
--------------

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

Dependencies
------------

This role depends on following roles:

Example Playbook
----------------
A reference playbook with required variables for this role.

**Add DNS**
    ---
    - hosts: vyos-2        
      roles:
        - role: get_config
          vars:
            action: "remove"
            network_name: "LAN"
            subnet: "192.168.0.0/24"
            range: "default_range"
            dhcp_start: "192.168.0.2"
            dhcp_end: "192.168.0.254"
            default_router: "192.168.0.1"
            dns_server: "8.8.8.8"
            lease: "86400"