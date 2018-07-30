# aptly

This role sets up a basic Aptly repository and configures a GPG key.
The GPG key is not regenerated when info is changed.

## Requirements

Debian

## Role Variables

| Name                        | Default / Mandatory        | Description                                                                                                  |
|:----------------------------|:--------------------------:|:-------------------------------------------------------------------------------------------------------------|
| `aptly_root_dir`            | `/var/lib/aptly`           | Root directory of the Aptly repository                                                                       |
| `aptly_gnupg_home`          | `/var/lib/aptly/.gnupg`    | Path to the Aptly GPG home                                                                                   |
| `aptly_gnupg_pkey_location` | `/var/lib/aptly/aptly.asc` | The public signing key is automatically exported to this location                                            |
| `aptly_gnupg_key_length`    | `4096`                     | Length of the signing key                                                                                    |
| `aptly_gnupg_name`          | `Aptly`                    | Real name of the key owner                                                                                   |
| `aptly_gnupg_email`         | `aptly@example.com`        | Email of the key owner                                                                                       |
| `aptly_configuration`       | `{}`                       | Configuration which is written to the JSON configuration file. `rootDir` is overridden with `aptly_root_dir` |
| `aptly_user`                | `root`                     | User that will own all Aptly-related files                                                                   |
| `aptly_group`               | `root`                     | Group that will own all Aptly-related files                                                                  |

## Example Playbook

```yml
- hosts: repo
  roles:
    - role: aptly
      aptly_gnupg_email: admin@example.com
```

## License

This work is licensed under a [Creative Commons Attribution-ShareAlike 4.0 International License](http://creativecommons.org/licenses/by-sa/4.0/).

## Author Information

- [Janne Heß](https://github.com/dasJ)
