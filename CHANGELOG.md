# Ansible Role for YUM

## 2.2.0 - TBC

### Major Changes

  - Allow fail when enable repos with RPM

### CentOS 7

  - Not enable CR Repo

## 2.1.0 - 2018-12-06

### Major Changes

  - CI with yamllint, ansible-lint and ansible-playbook --syntax-check
  - CI with LXD, improve systemd support
  - Ensure python related packages are up-to-date
  - Enable EPEL, ELRepo and IUS manually
  - Disable yum-plugin-fastestmirror which dramatically slow down Ansible

## 2.0.0 - 2018-10-25

### Major Changes

  - Upgrade Ansible support to 2.6 or higher
  - Support both Ubuntu RHEL/CentOS 6/7
  - Remove support for optional package installation
  - Keep YUM cache as-is
  - Update Travis CI test plan

## 1.1.0 - 2017-11-23

### Major Changes

  - Update test cases

## 1.0.0 - 2017-09-25

  - Ininitial release for Ansible 2.4
  - Support both RHEL/CentOS 7/6
