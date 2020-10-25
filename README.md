# Ansible Role : sync_sudo

[![Ansible Molecule](https://github.com/glillico/ansible-role-sync_sudo/workflows/Ansible%20Molecule/badge.svg)](https://github.com/glillico/ansible-role-sync_sudo/actions?query=workflow%3AAnsible%20Molecule)

This role syncronises the contents of the `files/etc/sudoers.d/` directory with the directory specified by `{{ sync_sudo_sudoers_dir }}` on the server.

The role will remove any files that exists on the server that does not have a match within the `/files/etc/sudoers.d` directory.

The files will be copied with the same permissisons as they currenlty have but will ignore both the owner and group permissisons, these will instead be set as the user who copied the files over.

## Requirements

This role required that the rsync package be installed on the server.

## Role Variables

    sync_sudo_sudoers_dir: /etc/sudoers.d

The directory where the sudoers files are stored in on the server.

## Dependencies

None.

## Example Playbook

    - hosts: servers
      vars_files:
        - vars/main.yml
      roles:
        - glillico.sync_sudo

## License

MIT

## Author Information

This role was created in 2020 by Graham Lillico.
