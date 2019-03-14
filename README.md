# Ansible role for PHP-FPM

[![CircleCI](https://circleci.com/gh/angristan/ansible-php-fpm.svg?style=svg)](https://circleci.com/gh/angristan/ansible-php-fpm)

This is a simple Ansible role for installing PHP-FPM with a set of modules and pools.

The role should work on all Debian-based distributions.

## Example playbook

```yaml
---

- hosts: myhost
  roles: phpf-fpm
  vars:
    php_version: 7.2
    php_modules:
      - mysql
      - curl
    php_fpm_pools:
      - name: blog
        pm_max_children: 10
        pm_start_servers: 4
        pm_min_spare_servers: 2
        pm_max_spare_servers: 6
    php_fpm_ini_options:
      - {option: post_max_size, value: 100M}
      - {option: upload_max_filesize, value: 100M}
      - {section: opcache, option: opcache.enable, value: 1}
```

## License

MIT

## Author Information

See my other Ansible roles at [angristan/ansible-roles](https://github.com/angristan/ansible-roles).
