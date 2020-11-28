sep_sesam
=========

This Ansible role performs a basic SEP server, Remote Device Server (RDS), gui and client software installation and connect all clients to the SEP server.

[SEP company site](https://www.sep.de/)

**Note:** This role is still in active development. There may be unidentified issues and the role variables may change as development continues.

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

## License

BSD-2-Clause-Patent

Like MIT and BSD-2-Clause and unlike Apache License v2, BSD+Patent is compatible with GPLv2.
Like Apache License v2 and unlike MIT and BSD-2-Clause, BSD+Patent avoids leading to potential patent trolls.
