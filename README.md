Ansible role: Sysctl
=========
Base role for manipulates sysctl entries.

Install
------------
```
ansible-galaxy install moletti.sysctl
```

Example playbook
------------
```yaml
- hosts: all
  gather_facts: yes
  vars:
    sysctl:
      - { name: net.ipv4.ip_forward, value : 1 }
  roles:
    - { role: moletti.sysctl, tags: sysctl }
```

Role Variables
--------------
|  variable      | type         | default | description                                                       |
|----------------|--------------|---------|-------------------------------------------------------------------|
| sysctl         | list(dict)   | []      | Sysctl entries                                              |
| sysctl_set     | bool         | yes     | Verify token value with the sysctl command                        |                             |
| sysctl_reload  | bool         | yes     | Performs a /sbin/sysctl -p if the sysctl_file is updated          |
| sysctl_state   | str          | []      | Whether the entry should be present or absent in the sysctl file. |                      |

sysctl:

|  Parameter |  required  |  default   | description                                                               | 
|------------|------------|------------|---------------------------------------------------------------------------| 
| name       |  +         |            | The dot-separated path (also known as key) specifying the sysctl variable |
| value      |  +         |            | Desired value of the sysctl key                                           |



LICENSE
-------
[MIT](/LICENSE)