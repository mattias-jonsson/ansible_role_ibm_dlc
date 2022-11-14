ansible_role_ibm_dlc
==============

This role perfoms the following actions

* Install/Upgrade IBM Java SDK though dependencies in meta/main.yml  
* Install/Upgrade/Configure IBM Disconnected Log Collector.

Requirements
---------------

Ansible collections used in this role:  
* ansible.posix

This role has been tested on the following Operating Systems.

* CentOS 7  
* CentOS 8  

Role variables
---------------

Variables used in the role:

    ansible_role_ibm_dlc_version:
    ansible_role_ibm_dlc_rpm:
    ansible_role_ibm_dlc_dest_type:
    ansible_role_ibm_dlc_dest_ip:
    ansible_role_ibm_dlc_dest_port:
    ansible_role_ibm_dlc_eps:
    ansible_role_ibm_dlc_release:


`ansible_role_ibm_dlc_version` Version of IBM DLC, default value 1.5.0.  
`ansible_role_ibm_dlc_rpm` Filename of IBM DLC installer.  
`ansible_role_ibm_dlc_dest_type` Protocol for logdestination, valid values are UDP/TCP, default value UDP.
`ansible_role_ibm_dlc_dest_ip` Destination IP for IBM Qradar destination, default value localhost.
`ansible_role_ibm_dlc_dest_port` Destination port for IBM Qradar destination, default value 32500.  
`ansible_role_ibm_dlc_eps` EPS limit. Default value 5000.  
`ansible_role_ibm_dlc_release` Release of IBM DLC, default value 1.


Sample configuration
---------------

```yaml
ansible_role_ibm_dlc_version: 1.5.0
ansible_role_ibm_dlc_release: 1
ansible_role_ibm_dlc_rpm: dlc-service-1.5.0-1.noarch.rpm
ansible_role_ibm_dlc_dest_type: udp
ansible_role_ibm_dlc_dest_ip: 'localhost'
ansible_role_ibm_dlc_dest_port: 32500
ansible_role_ibm_dlc_eps: 5000
```
