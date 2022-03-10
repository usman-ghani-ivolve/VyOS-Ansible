Firewall
=========

This role configure firewall.

Requirements
------------

- Management Network configuration with done with cloud-init
- SSH service is enable and listening on Management IP.

Role Variables
--------------
**Add Ruleset**
```
firewall_function
name
default_action
rule_set_description
enable_default_log
direction
interface
```
**Remove Ruleset**
```
firewall_function
name
direction
interface
```
**Add Rule**
```
firewall_function
name
rule_number
action
rule_description
destination_address
destination_address_group
destination_network_group
destination_port_group
destination_port
source_address
source_address_group
source_network_group
source_port_group
source_port
protocol
disabled
state
```
**Remove Rule**
```
firewall_function
name
rule_number
```
**Add Address/Network/Port Group**
```
action
type
group_name
group_description
members
```
**Remove Address/Network/Port Group**
```
action
type
group_name
```
**Add/Remove Address/Network/Port Member**
```
action
type
group_name
member
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
        - role: firewall
          vars:
            name: "myruleset-1"
            rule_number: "10"
            action: "accept"
            rule_description: "ruledesc"
            destination_address: ""
            destination_address_group: ""
            destination_network_group: ""
            destination_port_group: ""
            destination_port: ""
            source_address: ""
            source_address_group: ""
            source_network_group: ""
            source_port_group: ""
            source_port: ""
            protocol: "tcp"
            disabled: "false"
            state: "{"new": "true"}"