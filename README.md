sep_sesam
=========

This Ansible role performs a basic SEP server, Remote Device Server (RDS), gui and client software installation and connect all clients to the SEP server.

[SEP company site](https://www.sep.de/)

[SEP installation](https://wiki.sepsoftware.com/wiki/index.php/4_4_3:SEP_sesam_Quick_Install_Guide)

[SEP troubleshooting](https://wiki.sepsoftware.com/wiki/index.php/Troubleshooting_Guide)

**Note:** This role is still in active development. There may be unidentified issues and the role variables may change as development continues.

This role is developed wit ansible version 2.9.7 and install SEP sesam version 4.4.3.84

## Warning

[delegate_to uses incorrect interpreter](https://github.com/ansible/ansible/issues/63180)

If working with different OS you must set the variable `ansible_python_interpreter` for the SEP server(s)

## Role Variables

The (minimal) variables that must be defined

### `sep_sesam_server:`

FQDN from the SEP server where the clients must be configured

This will be mostly configured in the `group_vars/all` but can be elsewhere when there are multiple SEP server in the environment.

### `sep_sesam_host_type:`

Defines the host type
Must be defined on the host level, posible values are
| srv | For a SEP server instance |
| rds | For a Remote Device Server |
| gui | For the GUI client |
| cli | For a backup client only |

## example playbook

```
---
- hosts: all
  become: True

  vars:
    sep_sesam_server: sep-server.example.com

  roles:
  - { role: erbap.sep_sesam, when: (sep_sesam_host_type is defined) }
...
```

## License

BSD-2-Clause-Patent

Like MIT and BSD-2-Clause and unlike Apache License v2, BSD+Patent is compatible with GPLv2.

Like Apache License v2 and unlike MIT and BSD-2-Clause, BSD+Patent avoids leading to potential patent trolls.
