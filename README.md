# ansible-ssh

This role configures SSH on a Linux machine.

[![Ansible Galaxy](https://img.shields.io/badge/ansible--galaxy-ansible--ssh-blue.svg)](https://galaxy.ansible.com/0x07cf/ansible-ssh/)

## Requirements

🎉 No requirements!

## Role Variables

| Variable                      | Default              | Choices                                          | Comments |
| ----------------------------- | -------------------- | ------------------------------------------------ | -------- |
| `ssh_port`                    | true                 | true, false                                      |          |
| `ssh_permit_root_login`       | prohibit-password    | yes, no, prohibit-password, forced-commands-only |          |
| `ssh_usedns`                  | false                | true, false                                      |          |
| `ssh_permit_empty_password`   | false                | true, false                                      |          |
| `ssh_challenge_response_auth` | false                | true, false                                      |          |
| `ssh_gssapi_auth`             | false                | true, false                                      |          |
| `ssh_x11_forwarding`          | false                | true, false                                      |          |
| `ssh_motd`                    | false                | true, false                                      |          |
| `ssh_whitelist`               | []                   | list of users                                    |          |
| `ssh_whitelist_groups`        | []                   | list of groups                                   |          |
| `ssh_config_path`             | /etc/ssh/sshd_config | path to config file                              |          |
| `ssh_daemon`                  | ssh                  | systemd service                                  |          |
| `ssh_state`                   | started              | started, stopped                                 |          |

## Dependencies

😎 No dependencies.

## Example Playbook

> [!WARNING]
>
> **If you want to set `ssh_permit_root_login` to 'yes' or 'no', you must quote the value!**
>
> If you set `ssh_permit_root_login: no`, Ansible will treat the value as a boolean instead of a string, breaking your SSH configuration.

```yaml
- hosts: all
  vars_files:
    - vars/main.yml
  roles:
    - ceru1ean.home.ssh
```

### Example `vars/main.yml`:

```yaml
ssh_port: 42069
ssh_permit_root_login: "no"
ssh_x11_forwarding: true
```

## License

MIT

See [LICENSE](LICENSE) to see the full text.

## Author Information

This role was authored by [0x07cf](https://0x07.cf).
