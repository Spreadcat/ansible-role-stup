# spreadcat.stup

This role will deploy a local installation of [stup][#github] (STandUP) and configure the basic settings as required.

## Requirements

This role needs access to <http://github.com> in order to retrieve a copy of [stup][#github] and install it.

It also requires a local installation of [GIT][#git], which will be automatically installed from the package manager if not already installed.

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

```yaml
stup_url_git_repository: 'https://github.com/iridakos/stup'
```

URL to the GitHub repository from where to install [stup][#github].

```yaml
stup_config_owner: "{{ lookup('env', 'USER') }}"
```

Sets the user name for which [stup][#github] will be installed.

```yaml
stup_config_group: "{{ lookup('env', 'USER') }}"
```

Set the group name for the user for which [stup][#github] will be installed.

```yaml
stup_config_path: "{{ lookup('env', 'HOME') }}/.config/stup.conf
```

Sets the path for the [stup][#github] configuration file.

```yaml
setup_config_categories_root: "{{ lookup('env', 'HOME') }}/stup"
```

Path to the storage directory for [stup][#github].

```yaml
stup_config_default_category: personal
```

String with the name of the default category.

```yaml
stup_config_stup_editor: "{{ lookup('env', 'EDITOR') }}"
```

String with the name of the default editor to use. Is being set to the environment variable `EDITOR`.

## Other variables

```yaml
stup_config_default_command: show
```

String setting the default command when [stup][#github] is being run without any parameters.

```yaml
stup_config_default_show_at: yesterday
```

String to define the default day to show for [stup][#github].

```yaml
stup_config_default_log_days: 2
```

Integer with the number of days to show in the log.

```yaml
stup_config_default_add_at: today
```

Default on where to add new entries.

```yaml
stup_config_default_edit_at:  today
```

Default on which day to edit.

```yaml
stup_config_default_copy_from: yesterday
```

Default source for the copy command.

```yaml
stup_config_default_copy_to: today
```

Defautl destination for the copy command.

```yaml
stup_config_default_pager: more
```

Default pager to use. Replace with `less` or any other.

## Dependencies

None

## Example Playbook

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

```yaml
---
- hosts: all
  vars:
    stup_config_categories_root: /data/stup
  roles:
     - role: spreadcat.stup
```

## License

BSD

## Author Information

This role is written an maintained by DBV.

[#github]: https://github.com/iridakos/stup
[#git]: https://git-scm.com/
