[![CircleCI](https://circleci.com/gh/andrewrothstein/ansible-wildfly.svg?style=svg)](https://circleci.com/gh/andrewrothstein/ansible-wildfly)
andrewrothstein.wildfly
=========

Installs [Wildfly](http://wildfly.org/).

Requirements
------------

See [meta/main.yml](meta/main.yml)

Role Variables
--------------

See [defaults/main.yml](defaults/main.yml)

Dependencies
------------

See [meta/main.yml](meta/main.yml)

Example Playbook
----------------

```yml
- hosts: servers
  roles:
    - andrewrothstein.wildfly
```

License
-------

MIT

Author Information
------------------

Andrew Rothstein <andrew.rothstein@gmail.com>
