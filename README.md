# spreadcat.stup

This role will deploy a local installation of [stup][#github] (STandUP) and configure the basic settings as required.

## Requirements

* This role needs access to <http://github.com> in order to retrieve a copy of [stup][#github] and install it.
* It also requires a local installation of [GIT][#git], which will be automatically installed from the package manager if not already installed.
* The role requires `gathered_facts: true` to be set.

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

```yaml
stup_config_categories_root: str
```

* Path to the STUP storage directory location. The default is a directory `stup` in the home directory of the current user.

```yaml
stup_config_default_category: str
```

* Default category for STUP entries.

```yaml
stup_config_path: str
```

* Default file path for STUP configuration file.

```yaml
stup_version: str
```

* Set the deployment version for the script. Each version must match an existing tag in the Git directory.

## Other Variables

```yaml
stup_config_default_add_at: str
```

* Default day that new entries will be added to when no day is specified.

```yaml
stup_config_default_command: str
```

* Default command of STUP when executed without any other parameters.

```yaml
stup_config_default_copy_from: str
```

* Default copy source for STUP from which entries will be copied to the destination source when no source is specified.

```yaml
stup_config_default_copy_to: str
```

* Default copy destination for STUP to which entries will be copied from source when no destination has been specified.

```yaml
stup_config_default_edit_at: str
```

* Default day to edit when no day has been specified.

```yaml
stup_config_default_log_days: int
```

* Number of logs to output by STUP from previous days where entries exist.

```yaml
stup_config_default_pager: str
```

* Program name with the pager to use for very long outputs. Tools like `more` or `less` are usually defined.

```yaml
stup_config_group: str
```

* Default group for STUP configuration files. Usually set to the group of the user running the role.

```yaml
stup_config_owner: str
```

* Default owner for STUP configuration files. Usually set to the user running the role.

```yaml
stup_config_stup_editor: str
```

* Default editor for editig the STUP markdown files.

```yaml
stup_path_binary: str
```

* Sets the name and location of the stup script file.

```yaml
stup_url_git_repository: str
```

* URL for downloading the STUP GIT repository.

```yaml
stup_install_bash_completion: bool
```

* Installs the bash completion for stup when being set to true.

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
