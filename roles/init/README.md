Role Name
=========

This role bootstrap router with **default** configurations.

Requirements
------------

- Management Network configuration with done with cloud-init
- SSH service is enable and listening on Management IP.

Role Variables
--------------

```
default.lan_interface
default.lan_ip
default.lan_subnet
default.dhcp_start
default.dhcp_end
default.default_router
default.dns_server
default.lease
default.snat_rule_number
default.wan_interface
default.lan_subnet
init.function
init.wan_ip
init.wan_gateway
```

Dependencies
------------

This role depends on following roles:
- interfaces
- services
- nat
- firewall

Example Playbook
----------------

    ---
    hosts: vyos-2        
    roles:
      - bootstrap
        vars:
          default.lan_interface: "eth2"
          default.lan_ip: "192.168.0.1"
          default.lan_subnet: "192.168.0.0/24"
          default.dhcp_start: "192.168.0.2"
          default.dhcp_end: "192.168.0.254"
          default.default_router: "192.168.0.1"
          default.dns_server: "8.8.8.8"
          default.lease: "86400"
          default.snat_rule_number: "100"
          default.wan_interface: "eth0"
          init.function: "bootstrap"
          init.wan_ip: "20.30.40.50"
          init.wan_gateway: "20.30.40.1"