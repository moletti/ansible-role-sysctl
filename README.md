Ansible role: Sysctl
=========
[![Ansible Role](https://img.shields.io/ansible/role/55607)](https://galaxy.ansible.com/moletti/sysctl) [![GitHub release (latest SemVer)](https://img.shields.io/github/v/release/moletti/ansible-role-sysctl)](https://github.com/moletti/ansible-role-sysctl/releases) [![GitHub Workflow Status](https://img.shields.io/github/workflow/status/moletti/ansible-role-sysctl/Ansible%20Molecule?label=test)](https://github.com/moletti/ansible-role-sysctl/actions/workflows/molecule.yml) [![Ansible Quality Score](https://img.shields.io/ansible/quality/55607)](https://galaxy.ansible.com/moletti/sysctl) [![Ansible Role](https://img.shields.io/ansible/role/d/55607)](https://galaxy.ansible.com/moletti/sysctl)

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
      - name: net.ipv4.ip_forward
        value : 1
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