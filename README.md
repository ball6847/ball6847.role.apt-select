Ansible Role : ball6847.role.apt-select
=======================================

Install and set apt mirror to the closest server using apt-select

Requirements
------------

- pip

Role Variables
--------------

**apt_select_version**: `2.0.0`

Version of apt-select to be installed, default to 2.0.0

**apt_select_ignore_period**: `1440`

Set a period of time in minutes, to skip the task if `/etc/apt/source.list` has been changed in this period. (default to 1 day)

**apt_select_country**: `US`

Server zone to perform a test with, default to US.

**apt_select_top_number**: `3`

Maximum number of server to return from test. However, only the first one will be picked up.


Dependencies
------------

none

Example Playbook
----------------

If you are fine with default variables, you could call the role like this.

```yml
- name: "Select closest mirror"
  hosts: all
  roles:
    - ball6847.role.apt-select
```

If you want to change mirror location to your country, you could pass variable to role like this.

```yml
- name: "Select closest mirror"
  hosts: all
  roles:
    - { role: "ball6847.role.apt-select", apt_select_country: "TH" }
```

License
-------

BSD

Author Information
------------------

Porawit Poboonma

Credits
-------

- [apt-select](https://github.com/jblakeman/apt-select) - Ubuntu Archive Mirror reporting tool for apt sources configuration.
