Role Name
=========

This role add/remove Elastic IP on router.

Requirements
------------

- Management Network configuration with done with cloud-init
- SSH service is enable and listening on Management IP.

Role Variables
--------------

```
action
default_wan_interface
eip_address
dnat_rule_number
dnat_translation_address
snat_rule_number
snat_source_address
```

Dependencies
------------

This role depends on following roles:

- interfaces
- nat

Example Playbook
----------------
A reference playbook with required variables for this role.

    ---
    - hosts: vyos-2        
      roles:
        - role: elastic_ip
          vars:
            action: "add"
            default_wan_interface: "eth0"
            eip_address: "20.30.40.250"
            dnat_rule_number: "10"
            dnat_translation_address: "192.168.0.100"
            snat_rule_number: "10"
            snat_source_address: "192.168.0.100"