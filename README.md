<!--
SPDX-FileCopyrightText: 2020 Helmholtz Centre for Environmental Research (UFZ)
SPDX-FileCopyrightText: 2020 Helmholtz-Zentrum Dresden-Rossendorf (HZDR)

SPDX-License-Identifier: Apache-2.0
-->

Keepalived_Role
==========

Role sets up Keepalived in a High Availability and Scalability context.

Requirements
------------

Any pre-requisites that may not be covered by Ansible itself or the role should be mentioned here. For instance, if the role uses the EC2 module, it may be a good idea to mention in this section that the boto package is required.

Role Variables
--------------

#### Compulsory Variables to be Changed for the Configuration File

###### Configure notification email address

Configure recipient of notification emails:

```yaml
notification_email: 'name@localhost'
```

###### Configure notification sender

Configure sender of notification emails:

```yaml
notification_email_from: 'keepalived@localhost'
```

###### Configure SMTP Server

Configure IP address or FQDN of SMTP server:

```yaml
smtp_server: '127.0.0.1'
```

###### Keepalived instance router ID

Set unique name of the Keepalived router:

```yaml
router_id: 'KEEPALIVED_1'
```

###### Keepalived instance network interface

Set network interface to which the floating IP address is associated:

```yaml
interface: 'enp0s8'
```

###### Keepalived instance state MASTER or BACKUP

Set the state of the Keepalived instance to MASTER or BACKUP:

```yaml
state: 'MASTER'
```

###### Keepalived instance priority

Set the priority of the Keepalived instance:

```yaml
priority: '200'
```

###### Keepalived instance weight

Set the weight of the Keepalived instance:

```yaml
weight: '2'
```

###### Keepalived instance virtual router ID

Set the virtual router ID of the Keepalived instance:

```yaml
virtual_router_id: '123'
```

###### Keepalived instance unicast source IP address

Set the unicast source IP address of the Keepalived instance:

```yaml
unicast_src_ip: '192.168.33.14'
```

###### Keepalived instance unicast peer IP addresses

Set the unicast peer IP addresses of the Keepalived instance:

```yaml
unicast_peer: 
  - '192.168.33.15'
  - '192.168.33.16'
```

###### Keepalived instance virtual IP address

Set the virtual IP address of the Keepalived instance:

```yaml
virtual_ip_address: '192.168.33.100'
```

###### Keepalived instance virtual IP address and network interface

Set the virtual IP address and network interface of the Keepalived instance:

```yaml
virtual_ipaddress_config: '192.168.33.100 dev enp0s8'
```

###### Keepalived instance authentication password

Set the authentication password of the Keepalived instance:

```yaml
auth_pass: 'changeme'
```

#### All other Default Variables

###### Keepalived version

Variable to pin the Keepalived version to a certain value:

```yaml
keepalived_version: '2.1.3'
```

###### List of dependencies of Keepalived

List of Keepalived dependencies to be installed:

```yaml
keepalived_dependencies:
  - 'build-essential'
  - 'curl'
  - 'gcc'
  - 'libssl-dev'
  - 'libnl-3-dev'
  - 'libnl-genl-3-dev'
  - 'libsnmp-dev'
```

###### IP address of Keepalived

IP-Address of Keepalived insatnce is auto-detected:

```yaml
keepalived_instance_ip: "{{ ansible_default_ipv4.address }}"
```

###### Directory to put the Keepalived installation into

Select a directory to install Keepalived into:

```yaml
keepalived_base_dir: '/usr/local/'
```

###### Keepalived binary name

Name of the Keepalived binary:

```yaml
keepalived_name: 'keepalived'
```

###### Keepalived sources directory

Directory which contains Keepalived sources:

```yaml
keepalived_dir: 'keepalived/'
```

###### Keepalived build directory

Directory to build Keepalived in:

```yaml
keepalived_build_dir: 'keepalived-2.1.3/'
```

###### Keepalived build directory path

Path to Keepalived build directory:

```yaml
keepalived_build_dir_path: '/usr/local/keepalived-2.1.3/'
```

###### Keepalived binaries directory

Directory which contains the Keepalived binaries:
 
```yaml
keepalived_sbin_dir: 'sbin/'
```

###### Keepalived binary path

Path to the Keepalived binary:

```yaml
keepalived_path: '/usr/local/keepalived-2.1.3/sbin/keepalived'
```

###### Keepalived Download URL

URL from which Keepalived can be downloaded:

```yaml
keepalived_download_url: 'https://www.keepalived.org/software/keepalived-2.1.3.tar.gz'
```

###### Keepalived configuration directory

Directory which contains Keepalived configuration files:

```yaml
keepalived_conf_dir: '/etc/keepalived/'
```

###### Keepalived configuration file path

Path to Keepalived configuration file:

```yaml
keepalived_conf_file_path: 'etc/keepalived/keepalived.conf'
```

###### Systemd service template file name

Name of the template file for Systemd service:

```yaml
keepalived_service_template: 'keepalived.service'
```

###### Systemd services directory

Directory into which the Keepalived service file is copied:

```yaml
keepalived_systemd_dir: '/etc/systemd/system/'
```

###### Keepalived service file name

Name of Keepalived service file:

```yaml
keepalived_service_file: 'keepalived.service'
```

###### Keepalived service template file path

Path to Keepalived service template file: 

```yaml
keepalived_service_template_file_path: '/usr/local/keepalived-2.1.3/keepalived/keepalived.service'
```

###### Keepalived service file path

Path to Keepalived service file:

```yaml
keepalived_service_file_path: '/etc/systemd/system/keepalived.service'
```

Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: username.rolename, x: 42 }

License
-------

[Apache-2.0](LICENSES/Apache-2.0.txt)

Author Information
------------------

HIFIS Software Team (please visit [HIFIS Software Webpage](https://software.hifis.net))
