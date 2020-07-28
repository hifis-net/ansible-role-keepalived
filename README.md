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

#### Compulsory variables which are not set per default

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

#### All other Default Variables

###### Keepalived version

Variable to pin the Keepalived version to a certain value:

```yaml
keepalived_version: '2.1.5'
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

###### Name of Keepalived user

Specify Keepalived user to be created for Keepalived:

```yaml
keepalived_user: 'keepalived'
```

###### Name of Keepalived group

Specify Keepalived group to be created for Keepalived:

```yaml
keepalived_group: 'keepalived'
```

###### Enable script security

Flag to enable script security to prevent script to run by root user 
if any part of the path is writable by a non-root user:

```yaml
set_script_security_flag: true
```

###### HAProxy user for executing Keepalived script

Specify HAProxy username to run Keepalived script under:

```yaml
haproxy_user: 'haproxy'
```

###### HAProxy group for executing Keepalived script

Specify HAProxy groupname to run Keepalived script under:

```yaml
haproxy_group: 'haproxy'
```

###### HAProxy process name to be checked by Keepalived script

Specify HAProxy process name to be checked Keepalived script:

```yaml
haproxy_process_name: 'haproxy'
```

###### Directory to put the Keepalived installation into

Select a directory to install Keepalived into:

```yaml
keepalived_base_dir: '/usr/local'
```

###### Keepalived binary name

Name of the Keepalived binary:

```yaml
keepalived_name: 'keepalived'
```

###### Keepalived build directory

Path to Keepalived build directory:

```yaml
keepalived_build_dir: "/usr/local/keepalived"
```

###### Keepalived sources directory

Directory which contains Keepalived sources:

```yaml
keepalived_dir: "/usr/local/keepalived/keepalived"
```

###### Keepalived binary path

Path to the Keepalived binary:

```yaml
keepalived_path: '/usr/local/keepalived/sbin/keepalived'
```

###### Keepalived Download URL

URL from which Keepalived can be downloaded:

```yaml
keepalived_download_url: 'https://www.keepalived.org/software/keepalived-2.1.5.tar.gz'
```

###### Keepalived configuration directory

Directory which contains Keepalived configuration files:

```yaml
keepalived_conf_dir: '/etc/keepalived'
```

###### Keepalived configuration file path

Path to Keepalived configuration file:

```yaml
keepalived_conf_file_path: '/etc/keepalived/keepalived.conf'
```

###### Systemd service template file name

Name of the template file for Systemd service:

```yaml
keepalived_service_template: 'keepalived.service'
```

###### Systemd services directory

Directory into which the Keepalived service file is copied:

```yaml
keepalived_systemd_dir: '/etc/systemd/system'
```

###### Keepalived service file name

Name of Keepalived service file:

```yaml
keepalived_service_file: 'keepalived.service'
```

###### Keepalived service template file path

Path to Keepalived service template file: 

```yaml
keepalived_service_template_file_path: '/usr/local/keepalived/keepalived/keepalived.service'
```

###### Keepalived service file path

Path to Keepalived service file:

```yaml
keepalived_service_file_path: '/etc/systemd/system/keepalived.service'
```

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

###### Keepalived instance state MASTER or BACKUP

Set the state of the Keepalived instance to MASTER or BACKUP:

```yaml
state: 'BACKUP'
```

###### Keepalived instance priority

Set the priority of the Keepalived instance:

```yaml
priority: '99'
```

###### Keepalived instance router ID

Set unique name of the Keepalived router:

```yaml
router_id: 'KEEPALIVED_2'
```

###### Keepalived instance weight

Adjust the priority by this weight:

```yaml
weight: '0'
```

###### Keepalived instance unicast source IP address

Set the unicast source IP address of the Keepalived instance:

```yaml
unicast_src_ip: '{{ ansible_default_ipv4.address }}'
```

###### Keepalived instance network interface

Set network interface to which the floating IP address is associated:

```yaml
interface: "{{ ansible_default_ipv4.interface }}"
```

###### Keepalived instance virtual IP address and network interface

Set the virtual IP address and network interface of the Keepalived instance:

```yaml
virtual_ipaddress_config: "{{ virtual_ip_address }} dev {{ interface }}"
```

###### Keepalived instance authentication password

Set the authentication password of the Keepalived instance:

```yaml
auth_pass: 'changeme'
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
