Role Name
=========

This role configure Port Forwarding.

Requirements
------------

- Management Network configuration with done with cloud-init
- SSH service is enable and listening on Management IP.

Role Variables
--------------

```
dnat_rule_number
default_wan_interface
port_fwd_protocol
port_fwd_destination_address
port_fwd_translation_address
port_fwd_destination_port
port_fwd_translation_port
```

Dependencies
------------

This role depends on following roles:

- nat

Example Playbook
----------------
A reference playbook with required variables for this role.

    ---
    - hosts: vyos-2        
      roles:
        - role: port_forward
          vars:
            port_fwd_function: "add"
            dnat_rule_number: "10"
            default_wan_interface: "eth0"
            port_fwd_protocol: "tcp"
            port_fwd_destination_address: "20.30.40.60"
            port_fwd_translation_address: "192.168.0.100"
            port_fwd_destination_port: "2222"
            port_fwd_translation_port: "22"