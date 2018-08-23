# Ansible Role: Compile ZSH

Compiles and installs the latest ZSH. Useful for systems that have old packages in the repos.

## Requirements

Root access on a Debian or RedHat system.

Get this role with `ansible-galaxy install issmirnov.compile_zsh`

## Role Variables

- `zsh_version`: version of ZSH sources to pull. Locked to variable to allow idempotency.
- `zsh_temp_dir`: scratch space for compilation. Defaults to `/tmp`
- `zsh_new_users`: list of users that should use the new shell
- `remove_system_zsh`: Remove the system installed zsh, if present.

## Example Playbook

```
- name: compile and install zsh on all hosts
  hosts: all
  vars:
    remove_system_zsh: yes
    zsh_new_users:
      - dev
  roles:
    - issmirnov.compile_zsh
```

## License

MIT

## Author Information

- Ivan Smirnov, https://ivansmirnov.name
