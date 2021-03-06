Stouts.postfix
==============

[![Build Status](http://img.shields.io/travis/Stouts/Stouts.postfix.svg?style=flat-square)](https://travis-ci.org/Stouts/Stouts.postfix)
[![Galaxy](http://img.shields.io/badge/galaxy-Stouts.postfix-blue.svg?style=flat-square)](https://galaxy.postfix.com/list#/roles/914)
[![Tag](http://img.shields.io/github/tag/Stouts/Stouts.postfix.svg?style=flat-square)]()

Ansible role which manage postfix

#### Requirements

Only tested on ubuntu for now.

#### Variables

```yaml
postfix_enabled: yes # The role is enabled

postfix_smtpd_use_tls: yes
postfix_myhostname: "{{inventory_hostname}}"
postfix_myorigin: $myhostname
postfix_smtp_sasl_auth_enable: yes
postfix_smtp_tls_cafile: "/etc/ssl/certs/Thawte_Premium_Server_CA.pem"
postfix_relayhost: "[smtp.gmail.com]:587"
postfix_mynetworks: "127.0.0.0/8 [::ffff:127.0.0.0]/104 [::1]/128"
postfix_inet_interfaces: loopback-only
postfix_mydestination: $mydomain, $myhostname, localhost.$mydomain, localhost

postfix_generic_maps: ""

postfix_smtp_sasl_user: "{{ansible_ssh_user}}"
postfix_smtp_sasl_password: ""
```

#### Usage

Add `Stouts.postfix` to your roles and set vars in your playbook file.

Example:

```yaml

- hosts: all

  roles:
    - Stouts.postfix

  vars:
    postfix_smtp_sasl_user: myemail@gmail.com
    postfix_smtp_sasl_password: mypassword

```

#### License

Licensed under the MIT License. See the LICENSE file for details.

#### Feedback, bug-reports, requests, ...

Are [welcome](https://github.com/Stouts/Stouts.postfix/issues)!
