Ansible Role for YUM
====================

[![Build Status](https://travis-ci.org/alvistack/ansible-role-yum.svg?branch=master)](https://travis-ci.org/alvistack/ansible-role-yum)
[![GitHub tag](https://img.shields.io/github/tag/alvistack/ansible-role-yum.svg)](https://github.com/alvistack/ansible-role-yum)
[![GitHub license](https://img.shields.io/github/license/alvistack/ansible-role-yum.svg)](https://github.com/alvistack/ansible-role-yum/blob/master/LICENSE)
[![Ansible Role](https://img.shields.io/badge/galaxy-alvistack.yum-blue.svg)](https://galaxy.ansible.com/alvistack/yum)

Ansible Role for CentOS YUM Initialization.

Requirements
------------

This role require Ansible 2.4 or higher.

This role was designed for CentOS 7/6.

Role Variables
--------------

<table>
<colgroup>
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
</colgroup>
<thead>
<tr class="header">
<th>parameter</th>
<th>required</th>
<th>default</th>
<th>choices</th>
<th>comments</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>yum</td>
<td>no</td>
<td><code>[]</code></td>
<td></td>
<td>Passing <code>list</code> of parameters to <a href="http://docs.ansible.com/ansible/yum_module.html">yum module</a>.</td>
</tr>
<tr class="even">
<td>yum_repository</td>
<td>no</td>
<td><code>[]</code></td>
<td></td>
<td>Passing <code>list</code> of parameters to <a href="http://docs.ansible.com/ansible/yum_repository_module.html">yum_repository module</a>.</td>
</tr>
</tbody>
</table>

Dependencies
------------

No additional role dependencies.

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

-   Code released under [Apache License 2.0](https://github.com/alvistack/ansible-role-yum/blob/master/LICENSE)
-   Docs released under [CC BY 4.0](http://creativecommons.org/licenses/by/4.0/)

Author Information
------------------

-   Wong Hoi Sing Edison
    -   <https://twitter.com/hswong3i>
    -   <https://github.com/hswong3i>

