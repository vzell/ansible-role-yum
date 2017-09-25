Ansible Role for YUM
====================

[![Build Status](https://travis-ci.org/alvistack/ansible-role-yum.svg?branch=master)](https://travis-ci.org/alvistack/ansible-role-yum)
[![GitHub release](https://img.shields.io/github/release/alvistack/ansible-role-yum.svg)](https://github.com/alvistack/ansible-role-yum)
[![GitHub license](https://img.shields.io/github/license/alvistack/ansible-role-yum.svg)](https://github.com/alvistack/ansible-role-yum/blob/master/LICENSE)
[![Ansible Role](https://img.shields.io/badge/galaxy-alvistack.yum-blue.svg)](https://galaxy.ansible.com/alvistack/yum)

Ansible Role for RHEL/CentOS YUM Initialization.

Requirements
------------

This role require Ansible 2.4 or higher.

This role was designed for RHEL/CentOS 7/6.

Role Variables
--------------

[defaults/main.yml](defaults/main.yml)

Dependencies
------------

[meta/main.yml](meta/main.yml)

Example Playbook
----------------

    - hosts: all
      roles:
        - role: yum
          yum_repository:
            - state: "present"
              name: "ius"
              description: "IUS Community Packages for Enterprise Linux {{ ansible_distribution_major_version }} - $basearch"
              baseurl: "https://dl.iuscommunity.org/pub/ius/stable/CentOS/{{ ansible_distribution_major_version }}/$basearch"
              gpgcheck: "no"
              enabled: "yes"
          yum:
            - { state: "latest", name: "ius-release" }

License
-------

-   Code released under [Apache License 2.0](LICENSE)
-   Docs released under [CC BY 4.0](http://creativecommons.org/licenses/by/4.0/)

Author Information
------------------

-   Wong Hoi Sing Edison
    -   <https://twitter.com/hswong3i>
    -   <https://github.com/hswong3i>

