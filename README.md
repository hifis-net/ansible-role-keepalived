<!--
SPDX-FileCopyrightText: 2020 Helmholtz Centre for Environmental Research (UFZ)
SPDX-FileCopyrightText: 2020 Helmholtz-Zentrum Dresden-Rossendorf (HZDR)

SPDX-License-Identifier: Apache-2.0
-->

Keepalived_Role
===============

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
keepalived_unicast_peers: 
  - '192.168.33.15'
  - '192.168.33.16'
```

###### Keepalived instance virtual IP address

Set the virtual IP address of the Keepalived instance:

```yaml
keepalived_virtual_ip_address: '192.168.33.100'
```

###### Optional: List of virtual IP address configs

If you need to configure multiple virtual IP addresses you can define this
optional variable. This takes precedence over `keepalived_virtual_ip_address`.

```yaml
keepalived_virtual_ipaddress_configs:
  - "10.0.10.15 dev eth0"
  - "10.0.11.15 dev eht1"
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

###### Binary folder for Keepalived executable

Binary folder to put the Keepalived executable into:

```yaml
keepalived_binary_dir: "/usr/local/sbin"
```

###### Source folder for Keepalived builds

Source folder to put the Keepalived build directories into:

```yaml
keepalived_src_dir: "/usr/local/src"
```

###### Keepalived build directory

Path to Keepalived build directory:

```yaml
keepalived_build_dir: "/usr/local/src/keepalived-2.1.5"
```

###### Keepalived sources directory

Directory which contains Keepalived sources:

```yaml
keepalived_dir: "/usr/local/src/keepalived-2.1.5/keepalived"
```

###### Keepalived built binary path

Path to the built Keepalived binary:

```yaml
keepalived_built_binary_path: '/usr/local/src/keepalived-2.1.5/sbin/keepalived'
```

###### Keepalived executable path

Path to the Keepalived executable:

```yaml
keepalived_executable_path: '/usr/local/sbin/keepalived'
```

###### Keepalived Download URL

URL from which Keepalived can be downloaded:

```yaml
keepalived_download_url: 'https://www.keepalived.org/software/keepalived-2.1.5.tar.gz'
```

###### Keepalived configuration file template name

Name of the template file for Keepalived configuration file

```yaml
keepalived_conf_template: 'keepalived.conf.j2'
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
keepalived_service_template: 'keepalived.service.j2'
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

###### Directory for Keepalived PID file

Specify in which directory the Keepalived PID file should be created:

```yaml
keepalived_pid_file_dir: "/run/keepalived"
```

###### Configure notification email address

Configure recipient of notification emails:

```yaml
keepalived_notification_email: 'name@localhost'
```

###### Configure notification sender

Configure sender of notification emails:

```yaml
keepalived_notification_email_from: 'keepalived@localhost'
```

###### Configure SMTP Server

Configure IP address or FQDN of SMTP server:

```yaml
keepalived_smtp_server: '127.0.0.1'
```

###### Keepalived instance state MASTER or BACKUP

Set the state of the Keepalived instance to MASTER or BACKUP:

```yaml
keepalived_state: 'BACKUP'
```

###### Keepalived instance priority

Set the priority of the Keepalived instance:

```yaml
keepalived_priority: '99'
```

###### Keepalived instance router ID

Set unique name of the Keepalived router:

```yaml
keepalived_router_id: 'KEEPALIVED_2'
```

###### Keepalived instance weight

Adjust the priority by this weight:

```yaml
keepalived_weight: '0'
```

###### Keepalived instance unicast source IP address

Set the unicast source IP address of the Keepalived instance:

```yaml
keepalived_unicast_src_ip: '{{ ansible_default_ipv4.address }}'
```

###### Keepalived instance network interface

Set network interface to which the floating IP address is associated:

```yaml
keepalived_interface: "{{ ansible_default_ipv4.interface }}"
```

###### Keepalived instance virtual IP address and network interface

Set the virtual IP address and network interface of the Keepalived instance:

```yaml
keepalived_virtual_ipaddress_config: "{{ keepalived_virtual_ip_address }} dev {{ keepalived_interface }}"
```

###### Keepalived instance authentication password

Set the authentication password of the Keepalived instance:

```yaml
keepalived_auth_pass: 'changeme'
```

###### Enable script security

Flag to enable script security to prevent script to run by root user 
if any part of the path is writable by a non-root user:

```yaml
keepalived_set_script_security_flag: true
```

###### User for executing Keepalived script

Specify username to run Keepalived script under:

```yaml
keepalived_script_user: 'haproxy'
```

###### Group for executing Keepalived script

Specify groupname to run Keepalived script under:

```yaml
keepalived_script_group: 'haproxy'
```

###### Flag to activate process tracking

Activate process tracking in keepalived config:

```yaml
keepalived_enable_process_tracking: true
```

###### Define which process shall be tracked

```yaml
keepalived_track_process: 'haproxy'
```

###### Flag to activate a script to be executed

Activate script that is executed by Keepalived:

```yaml
keepalived_activate_script: false
```

###### Name of the script to be executed

Specify the script name to be executed by Keepalived:

```yaml
keepalived_script_name: 'chk_haproxy_process'
```

###### Command of the script to be executed

Specify the command to be executed by Keepalived:

```yaml
keepalived_script_command: '/usr/bin/killall -0 haproxy'
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
