# Ansible Role for Diffie-Hellman parameters

[![Build Status][1]][2]

Generates [Diffie-Hellman parameters][3] on Debian/Ubuntu servers.

## Requirements

When generating the parameters on your local machine, you need `openssl` installed.
It is recommended that you set `dhparam_create_on_local_machine` to `yes`.

## Role Variables

```
dhparam_create_on_local_machine: no
dhparam_size: 4096
dhparam_path: "/etc/ssl/certs/dhparam-{{ dhparam_size }}.pem"
# (no, reboot, hourly, daily, weekly, monthly, annually, yearly)
dhparam_periodic_update: no
```

## Role Tags

Each part of the setup has a tag.

```
dhparam:install
dhparam:cron
```

## Dependencies

None.

## Example Playbook

```
---
- hosts: servers
  become: yes
  roles:
    - noplanman.dhparam
```

## License

MIT

[1]: https://travis-ci.org/noplanman/ansible-role-dhparam.svg?branch=master "Travis-CI Build Status"
[2]: https://travis-ci.org/noplanman/ansible-role-dhparam "Travis-CI Tests"
[3]: https://raymii.org/s/tutorials/Strong_SSL_Security_On_nginx.html#Forward_Secrecy_&_Diffie_Hellman_Ephemeral_Parameters "Diffie-Hellman parameters"
