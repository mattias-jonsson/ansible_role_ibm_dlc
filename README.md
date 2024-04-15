Ansible Role: ibm_dlc
==============

This role perfoms the following actions

Installs/upgrade/configure IBM Disconnected Log Collector on the following Operating Systems:

<ul>
<li> Enterprise Linux 7/8/9
</ul>

Requirements
---------------

This role requires the `ansible.posix` Ansible collection. If not already installed, you can install it using the following command:

```shell
ansible-galaxy collection install ansible.posix
```

Role Variables
--------------

Available variables are listed below, along with default values where applicable (see `defaults/main.yml`):

| Variable | Required | Default | Comments |
| -------- | -------- | ------- | -------- |
| `ibm_dlc_dest_ip` | Yes | | Specifies the IP address of the IBM QRadar deployment designated to receive logs. |
| `ibm_dlc_dest_port` | No | 32500 | Defines the port on the IBM QRadar deployment. The default port is 32500. |
| `ibm_dlc_dest_proto` | No | udp | Specifies the protocol used for sending logs to the IBM QRadar deployment. Supported values are udp and tcp, with udp being the default. |
| `ibm_dlc_eps` | No | 5000 | Sets the Events Per Second (EPS) limit for log transmission. The default limit is set to 5000. Adjust according to your logging requirements. |
| `ibm_dlc_installer_sha256sum` | No | Defaults in `defaults/main.yml` | Provides a mapping of IBM DLC installer filenames to their respective SHA256 checksums, ensuring integrity and authenticity of the installer files. Refer to defaults/main.yml for specific values. |
| `ibm_dlc_installer` | Yes | | URL or local path, including filename, of the installer. |
| `ibm_dlc_metrics_enabled` | No | true | Enables or disables the collection of performance metrics by the IBM DLC. This is enabled by default. |
| `ibm_dlc_print_instanceid` | No | False | Controls whether the IBM DLC instance ID should be logged in the playbook output. Default is false.  |
| `ibm_dlc_tls_version` | No | 1.2 | Specifies the version of the TLS protocol used. |
| `ibm_dlc_version` | No | Dynamic based on ibm_dlc_installer | Automatically determines the version of the IBM DLC based on the installer filename. |

Dependencies
------------

This role depends on `mattias-jonsson.ibm_java_sdk` If not already installed, you can install it using the following command:

```shell
ansible-galaxy role install mattias-jonsson.ibm_java_sdk
```

Example Playbook
----------------

```shell
- hosts: servers

  vars:
    ibm_dlc_dest_ip: '192.168.0.1'
    ibm_dlc_dest_port: 32500
    ibm_dlc_dest_proto: udp
    ibm_dlc_eps: 5000
    ibm_dlc_installer: http://192.168.1.100/dlc-service-1.5.0-1.noarch.rpm
    ibm_dlc_print_instanceid: true

    ibm_java_sdk_version: 8.0-8.21
    ibm_java_sdk_set_default_java: true

  roles:
      - ansible_role_ibm_dlc
```

License
-------

MIT

Author Information
------------------

Mattias Jonsson
