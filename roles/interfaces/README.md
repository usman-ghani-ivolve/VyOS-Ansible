Interfaces
=========

This role configure router interfaces.

Requirements
------------

- Management Network configuration with done with cloud-init
- SSH service is enable and listening on Management IP.

Role Variables
--------------
**Configure Subnet**
```
network_function
network_interface
network_ip_address
network_old_ip_address
dhcp_action
dhcp_enabled
network_name
dhcp_subnet
dhcp_range
dhcp_start
dhcp_end
default_router
dhcp_old_subnet
```
**Configure Gatteway**
```
network_function
network_interface
network_ip_address
network_subnet
network_old_ip_address
dhcp_action
dhcp_enabled
network_name
default_router
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
        - role: interfaces
          vars:
            network_function: "configure_gateway"
            network_interface: "eth2"
            network_subnet: "192.168.0.0/24"
            network_ip_address: "192.168.0.254/24"
            network_old_ip_address: "192.168.0.1"
            dhcp_enabled: "true"
            network_name: "LAN"
            default_router: "192.168.0.254"