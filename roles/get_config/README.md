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
resource
```

Dependencies
------------

This role depends on following roles:

Example Playbook
----------------
A reference playbook with required variables for this role.

    ---
    - hosts: vyos-2        
      roles:
        - role: get_config
          vars:
            resource: "l3_interfaces"