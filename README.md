Ansible Role: Airbyte
=========

This role installs and runs Airbyte on Linux hosts.

Requirements
------------

Requires Docker or and Compose. Recommended role for Docker installation: geerlingguy.docker.

Role Variables
--------------

Available variables are listed below, along with default values (see `defaults/main.yml`):

    airbyte_version: '0.35.2-alpha'
    airbyte_docker_path: '/usr/loca/usr/airbyte'
    airbyte_proxy_mode: no

    airbyte_database_host: db
    airbyte_database_port: 5432
    airbyte_database_user: docker
    airbyte_database_pass: docker
    airbyte_database_name: airbyte

Using "Proxy mode", Airbyte will be available from 127.0.0.1 only.

Connecting to an external database:

    airbyte_database_host: my-postgresql.io
    airbyte_database_port: 5432
    airbyte_database_user: airbyte
    airbyte_database_pass: changeme
    airbyte_database_name: airbyte

Dependencies
------------

Requires Docker or and Compose. Recommended role for Docker installation: geerlingguy.docker.

Example Playbook
----------------

    - hosts: all
      roles:
        - samber.airbyte

Contribute
----------

Update server address into tests/inventory.

```
cd tests/

ansible-galaxy install -r requirements.yml --force
ansible-playbook playbook.yml -i inventory
```

License
-------

MIT

Sponsors
--------

[Screeb](https://screeb.app): Transform User Insights into Faster Decisions

Author Information
------------------

This role was created in 2022 by Samuel Berthe.
