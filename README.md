Ansible Role: ansible_role_ibm_dlc
==============

This role perfoms the following actions

Installs/upgrade IBM Java SDK though dependencies in meta/main.yml, installs/upgrade/configure IBM Disconnected Log Collector on the following Operating Systems:

<ul>
<li> Enterprise Linux 7/8
</ul>

Requirements
---------------

This role is dependent on the following Ansible collections:
`ansible.posix`

Role Variables
--------------

Available variables are listed below, along with default values where applicable (see `defaults/main.yml`):


Role variables
---------------

| Variable | Required | Default | Comments |
| -------- | -------- | ------- | -------- |
| `ansible_role_ibm_dlc_dest_ip` | Yes | localhost | Destination IP for IBM Qradar destination, default value localhost. |
| `ansible_role_ibm_dlc_dest_port` | Yes | 32500 | Destination port for IBM Qradar destination, default value 32500. |
| `ansible_role_ibm_dlc_dest_type` | Yes | udp | Protocol for logdestination, valid values are UDP/TCP, default value UDP. |
| `ansible_role_ibm_dlc_eps` | Yes | 5000 | EPS limit. Default value 5000. |
| `ansible_role_ibm_dlc_release` | Yes | 1 | Release of IBM DLC, default value 1. |
| `ansible_role_ibm_dlc_rpm` | Yes | dlc-service-{{ ansible_role_ibm_dlc_version }}-{{ ansible_role_ibm_dlc_release }}.noarch.rpm | Filename of IBM DLC installer.  |
| `ansible_role_ibm_dlc_version` | Yes | 1.5.0 | Version of IBM Distributed Log Collector to install. |

Dependencies
------------

This role depends on `https://github.com/mattias-jonsson/ansible_role_ibm_java_sdk`.

Example Playbook
----------------

    - hosts: servers

      vars:
        ansible_role_ibm_dlc_dest_ip: 'localhost'
        ansible_role_ibm_dlc_dest_port: 32500
        ansible_role_ibm_dlc_dest_type: udp
        ansible_role_ibm_dlc_eps: 5000
        ansible_role_ibm_dlc_release: 1
        ansible_role_ibm_dlc_rpm: dlc-service-1.5.0-1.noarch.rpm
        ansible_role_ibm_dlc_version: 1.5.0

      roles:
         - ansible_role_ibm_dlc

License
-------

MIT

Author Information
------------------

Mattias Jonsson

