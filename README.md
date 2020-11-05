# Ansible Role: PHP-PostgreSQL

[![CI](https://github.com/geerlingguy/ansible-role-php-pgsql/workflows/CI/badge.svg?event=push)](https://github.com/geerlingguy/ansible-role-php-pgsql/actions?query=workflow%3ACI)

Installs PHP [PostgreSQL](https://www.postgresql.org/) support on Linux.

## Requirements

None.

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

    php_enablerepo: ""

(RedHat/CentOS only) If you have enabled any additional repositories (might I suggest geerlingguy.repo-epel or geerlingguy.repo-remi), those repositories can be listed under this variable (e.g. `remi,epel`). This can allow you to install later versions of PHP packages.

    php_pgsql_package: php-pgsql # RedHat
    php_pgsql_package: php7.0-pgsql # Debian

The PHP PostgreSQL package to install via apt/yum. This should only be overridden if you need to install a unique/special package for PostgreSQL support, as in the case of using software collections on Enterprise Linux.

## Dependencies

  - geerlingguy.php

## Example Playbook

    - hosts: webservers
      roles:
        - geerlingguy.postgresql
        - geerlingguy.php
        - geerlingguy.php-pgsql

## License

MIT / BSD

## Author Information

This role was created in 2016 by [Jeff Geerling](https://www.jeffgeerling.com/), author of [Ansible for DevOps](https://www.ansiblefordevops.com/).
