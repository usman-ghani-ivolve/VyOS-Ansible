Bootstrap
=========

This role bootstrap router with **default** configurations.

Requirements
------------

- Management Network configuration with done with cloud-init
- SSH service is enable and listening on Management IP.

Role Variables
--------------

```
default_lan_interface
default_lan_ip
default_lan_subnet
default_dhcp_start
default_dhcp_end
default_default_router
default_dns_server
default_lease
default_snat_rule_number
default_wan_interface
wan_ip
wan_gateway
```

Dependencies
------------

This role depends on following roles:
- interfaces
- dhcp
- nat
- firewall

Example Playbook
----------------
A reference playbook with required variables for this role.

    ---
    - hosts: vyos-2        
      roles:
        - role: bootstrap
          vars:
            default_lan_interface: "eth2"
            default_lan_ip: "192.168.0.1"
            default_lan_subnet: "192.168.0.0/24"
            default_dhcp_start: "192.168.0.2"
            default_dhcp_end: "192.168.0.254"
            default_default_router: "192.168.0.1"
            default_dns_server: "8.8.8.8"
            default_lease: "86400"
            default_snat_rule_number: "100"
            default_wan_interface: "eth0"
            wan_ip: "20.30.40.50"
            wan_gateway: "20.30.40.1"