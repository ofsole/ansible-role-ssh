ansible-role-ssh
=========

[![Build Status](https://travis-ci.org/ofsole/ansible-role-ssh.png?branch=master)](https://travis-ci.org/ofsole/ansible-role-ssh)

Ansible role manages ssh client and ssh server

Requirements
------------

Any pre-requisites that may not be covered by Ansible itself or the role should be mentioned here. For instance, if the role uses the EC2 module, it may be a good idea to mention in this section that the boto package is required.

Role Variables
--------------

Here is a list of all the default variables for this role, which are also available in `defaults/main.yml`.

```
# defaults file for ssh client
permit_root_login: 'yes'
ssh_config_path: /etc/ssh/ssh_config
ssh_config_owner: root
ssh_config_group: root
ssh_config_mode: 644
ssh_config_sendenv_xmodifiers: false
ssh_config_template: ssh_config.j2
ssh_gssapiauthentication: 'yes'
ssh_key_ensure: present
ssh_key_import: true
ssh_key_type: ssh-rsa
ssh_config_global_known_hosts_file: /etc/ssh/ssh_known_hosts
ssh_config_global_known_hosts_owner: root
ssh_config_global_known_hosts_group: root
ssh_config_global_known_hosts_mode: 644
ssh_config_ciphers: []
ssh_config_forward_agent: ""
ssh_config_forward_x11: ""
ssh_config_server_alive_interval: ""
ssh_config_macs: []
manage_root_ssh_config: false
root_ssh_config_content: "# This file is being maintained by Ansible.\n# DO NOT EDIT\n"
ssh_gssapidelegatecredentials: ""
# defaults file for ssh server(sshd)
sshd_config_path: /etc/ssh/sshd_config
sshd_config_owner: root
sshd_config_group: root
sshd_config_loglevel: INFO
sshd_config_port: 22
sshd_config_syslog_facility: AUTH
sshd_config_template: sshd_config.j2
sshd_config_login_grace_time: 120
sshd_config_challenge_resp_auth: 'yes'
sshd_config_print_motd: 'yes'
sshd_config_banner: none
sshd_config_allowgroups: []
sshd_config_allowusers: []
sshd_config_denygroups: []
sshd_config_denyusers: []
sshd_config_strictmodes: ""
sshd_config_authkey_location: ""
sshd_banner_owner: root
sshd_banner_group: root
sshd_banner_mode: 644
sshd_password_authentication: 'yes'
sshd_allow_tcp_forwarding: 'yes'
sshd_x11_forwarding: 'yes'
sshd_client_alive_count_max: 3
sshd_client_alive_interval: 0
sshd_gssapiauthentication: 'yes'
sshd_hostbasedauthentication: 'no'
sshd_ignoreuserknownhosts: 'no'
sshd_ignorerhosts: 'yes'
sshd_listen_address: []
manage_service: true
sshd_addressfamily: any
sshd_authorized_keys_command: ""
sshd_authorized_keys_command_user: ""
sshd_config_maxstartups: ""
sshd_config_maxsessions: ""
sshd_config_chrootdirectory: ""
sshd_config_forcecommand: ""
sshd_config_ciphers: []
sshd_config_macs: []
sshd_config_match: {}
sshd_kerberos_authentication: ""
service_state: started
service_enable: 'yes'
service_hasrestart: true
```

Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
        - role: ssh
      vars:
        permit_root_login: no
        package:
          - openssh-server
          - openssh-client
        service_name: sshd
        sshd_config_subsystem_sftp: '/usr/libexec/openssh/sftp-server'

License
-------

BSD

Author Information
------------------

Elvis Cai
