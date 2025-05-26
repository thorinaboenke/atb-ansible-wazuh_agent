Role Name
=========

Installs a very simple wazuh-agent setup. This role is just for the [attackbed](https://github.com/ait-testbed/attackbed.git). 
For more advanced installations please use the official [wazuh-ansible roles](https://github.com/wazuh/wazuh-ansible/)

Requirements
------------

- Debian/Ubuntu

Role Variables
--------------

```
wazuh_repokey: "https://packages.wazuh.com/key/GPG-KEY-WAZUH"
wazuh_repourl: "https://packages.wazuh.com/4.x/apt/ stable main"
# wazuh_localfiles:
#   - log_format: apache
#     location: /var/log/apache2/access.log
#   - log_format: json
#     location: /var/log/suricata/eve.json
wazuh_localfiles: []
wazuh_manager: false
```

Please not that `wazuh_manager` must be set with a correct ip address!

Dependencies
------------

None

Example Playbook
----------------

```
- hosts: localhos
  become: true
  roles:
    - role: wazuh_agent
      vars:
        wazuh_manager: 192.168.100.130
        wazuh_localfiles:
          - log_format: apache2
            location: /var/log/apache2/access.log
          - log_format: json
            location: /var/log/suricata/eve.json
```

License
-------

GPL-3.0-only

Author Information
------------------

Wolfgang Hotwagner(AIT Austrian Institute of Technology)
