
# Ansible Role - potos\_mimeapps

This role is used to configure the default apps to be called e.g. from
a browser for a `mailto` link. It translates the settings defined
in the role variable into `/etc/xdg/mimeapps.list`. See below for
the example default settings of that variable.

## Example Playbook

As this role is **not yet** tested via Molecule one can use [that
playbook](./molecule/default/converge.yml) as a starting point:

```yaml
---

- name: Converge
  hosts: all
  gather_facts: yes
  tasks:
    - name: run role
      ansible.builtin.include_role:
        name: 'ansible-role-potos_template'
```

## Role Variables

The default variable is defined in [defaults/main.yml](./defaults/main.yml):

```yaml
---

# mimetype / desktop associations, for two sections in mimeapps.list
potos_mimeapps:
  default_applications:
    - mimetype: video/mp4
      desktop: vlc.desktop
    - mimetype: x-scheme-handler/mailto
      desktop: claws-mail.desktop
  added_associations:
    - mimetype: video/mp4
      desktop: vlc.desktop
    - mimetype: video/webm
      desktop: vlc.desktop
    - mimetype: x-scheme-handler/mailto
      desktop: claws-mail.desktop
```

Another option is to use `ansible-doc` to read the argument specification:

```sh
ansible-doc --type role -r . main ansible-role-potos_template
```

## Requirements

N/A

## License

See [LICENSE](./LICENSE)

## Author Information

[Project Potos](https://github.com/projectpotos)

