# role-users

Ansible role to manage users and groups on Linux systems.

The role can configure a user on the system with or initialize a user if the user is a remote one, like if defined on an LDAP server.
The role can also manage groups, user's group and group membership.

## Requirements

The role requires:
 - RHEL/CentOS >= 6
 - Debian >= 7
 - Ubuntu >= 14

## Role Variables

The variables are fully documented in the [default configuration](defaults/main.yml) file, including their default values and some examples. This file contains all the settings that can be configured.

Please refer to the default configuration file for the full list and use Linux man pages if you need more information on Sudo.

| Variable        | Default | Description         |
| :---            | :---    | :---                |
| `system_groups` | `[]`    | Groups definitions. |
| `system_users`  | `[]`    | Users definitions.  |

## Example Playbook

Using the role without any specific configuration is very simple:

```Yaml
- hosts: servers
  roles:
   - role: users
     system_groups:
      - name:     users
     system_users:
      - username: alice
        group:    users
        groups:   wheel
        password: Passw0rd
        type:     local
```

## License

MIT

## Author Information

[Fabrizio Colonna](colofabrix@tin.it)

## Contributors

Pull requests are also very welcome. Please create a topic branch for your proposed changes. If you don't, this will create conflicts in your fork after the merge.
