# Ansible Role Skeleton

Role skeleton for all collections under the `marcstraube` namespace.

## Usage

```bash
ansible-galaxy role init \
  --role-skeleton=path/to/ansible-role-skeleton/skeleton \
  -e collection_name=common \
  my_new_role
```

This generates a complete role with:

- `defaults/main.yml` with standard section structure
- `tasks/` with dispatcher pattern (main, install, configure, service, btrfs, firewall, apparmor)
- `handlers/main.yml` with restart/reload handlers
- `vars/` for Arch, Debian, RedHat OS-specific variables
- `molecule/default/` with podman config for all 4 platforms
- `meta/main.yml` with Galaxy metadata
- `README.md` with standard documentation structure

## After Init

Delete what you don't need:

| Not needed | Delete | Remove from |
| ---------- | ------ | ----------- |
| No daemon/service | `handlers/main.yml`, `tasks/service.yml` | `tasks/main.yml`, `defaults/main.yml` |
| No BTRFS | `tasks/btrfs.yml` | `tasks/main.yml`, `defaults/main.yml` |
| No firewall | `tasks/firewall.yml` | `tasks/main.yml`, `defaults/main.yml` |
| No AppArmor | `tasks/apparmor.yml` | `tasks/main.yml`, `defaults/main.yml` |

Fill in all `TODO` markers across the generated files.

## Conventions

See `docs/role-template.md` in the main `ansible-infrastructure` repo for the
full coding conventions reference.

## License

MIT
