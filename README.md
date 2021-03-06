<img src="http://www.elao.com/images/corpo/logo_red_small.png"/>

# Ansible Role: SSH

This role will assume the following configuration:
- Allow sudo authentication over ssh
- Enable/Disable the SSH daemon password authentication
- Set the SSH daemon accepted environment variables
- Set ssh know hosts

It's part of the ELAO [Ansible stack](http://ansible.elao.com) but can be used as a stand alone component.

## Requirements

- Ansible 1.7.2+

## Dependencies

None.

## Installation

### Ansible 2+

Using ansible galaxy cli:

```bash
ansible-galaxy install elao.ssh,2.0
```

Using ansible galaxy requirements file:

```yaml
- src:     elao.ssh
  version: 2.0
```

### Ansible 1 (no longer maintained)

Using ansible galaxy cli:

```bash
ansible-galaxy install elao.ssh,1.0
```

Using ansible galaxy requirements file:

```yaml
- src:     elao.ssh
  version: 1.0
```

## Role Handlers

|Name|Action|Description|
|----|----|-----------|-------|
`sudo restart`|Service restarted|Ensure sudo service has been restarted.
`ssh reload`|Service reloaded|Ensure ssh service has been reloaded.

## Role Variables

|Name|Default|Type|Description|
|----|----|-----------|-------|
`elao_ssh_known_hosts`|Empty collection|Collection|Ssh known hosts.
`elao_ssh_sudo_auth`|false|Binary|Allow sudo authentication over ssh.
`elao_ssh_config.daemon.password_authentication`|true|Binary|Enable/Disable the SSH daemon password authentication.
`elao_ssh_config.daemon.accept_env`|LANG LC_*|String|SSH daemon accepted environment variables.

## Example playbook

    - hosts: servers
      roles:
         - { role: elao.ssh }

# Licence

MIT

# Author information

ELAO [**(http://www.elao.com/)**](http://www.elao.com)