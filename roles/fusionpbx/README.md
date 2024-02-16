Role Name
=========

FusionPBX 5.2 installer. Created by converting the original [fusionpbx-install script](https://github.com/fusionpbx/fusionpbx-install.sh)

Requirements
------------

Set proper values for variables before running, many will require deleting the DB cluster to change later with this script

Role Variables
--------------

| Variable | Default | Options | Description |
|---|---|---|---|
| domain_name | hostname | hostname, ip_v4, ip_v6, * | Sets the default domain to the system hostname, v4/v6 address, or other provided name |
| system_username | admin | * | System superadmin username |
| system_password | not_secure | * | System superadmin password |
| system_branch | 5.2 | * | FusionPBX branch tag |
| switch_branch | stable | * | FreeSWITCH branch tag |
| switch_source | true | true, false | Build FreeSWITCH from source |
| switch_package | false | true, false | Install FreeSWITCH from package |
| switch_version | 1.10.10 | * | FreeSWITCH version |
| switch_tls | true | true, false | Enable TLS on FreeSWITCH (not currently used) |
| switch_token | null | * | SignalWire token for FreeSWITCH repository |
| sofia_version | 1.13.17 | * | Sofia SIP version |
| database_name | fusionpbx | * | PostgreSQL database name |
| database_username | fusionpbx | * | PostgreSQL database username |
| database_password | not_secure | * | PostgreSQL database password |
| database_repo | official | official, system | What repository to download PostgreSQL from |
| database_version | 16 | * | PostgreSQL major version to use |
| database_host | 127.0.0.1 | * | PostgreSQL host, will install db if 127.0.0.1 or ::1 |
| database_port | 5432 | * | PostgreSQL port |
| database_backup | false | true, false | Enable database backup cron job |
| database_initial_setup | true | true, false | Seed database with initial domain, superadmin, and app defaults |
| php_version | 8.1 | 7.1, 7.3, 7.4, 8.1 | PHP version to use |
| letsencrypt | true | true, false | Enable Lets Encrypt (not currently used) |


Dependencies
------------

geerlingguy.php-versions and geerlingguy.php are required.

Example Playbook
----------------

    - name: FusionPBX
      hosts: tag_fusionpbx
      roles:
        - fusionpbx

License
-------

BSD

Author Information
------------------

David Fiel, https://fiel.solutions
