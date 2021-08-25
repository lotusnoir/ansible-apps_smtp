# Ansible Role: ansible-apps_smtp_exporter

## Description

[![Build Status](https://travis-ci.com/lotusnoir/ansible-apps_smtp_exporter.svg?branch=master)](https://travis-ci.com/lotusnoir/ansible-apps_smtp_exporter)[![License](https://img.shields.io/badge/license-Apache--2.0-brightgreen)](https://opensource.org/licenses/Apache-2.0)[![Ansible Role](https://img.shields.io/badge/ansible%20role-apps__smtp_exporter-blue)](https://galaxy.ansible.com/lotusnoir/ansible-apps_smtp_exporter/)[![GitHub tag](https://img.shields.io/badge/version-latest-blue)](https://github.com/lotusnoir/ansible-apps_smtp_exporter/tags)

Deploy postfix and use it as relay host through mailjet.

## Role variables

| Name                    | Default Value            | Description                        |
| ----------------------- | ------------------------ | -----------------------------------|
| `mailjet_username`      |                          | mailjet username |
| `mailjet_password`      |                          | mailjet user password |
| `mailjet_relay`         | [in-v3.mailjet.com]:587  | mailjet server |
| `saslauthd_enable`      | yes                      | Activation of the sasl auth support |
| `saslauthd_ldap_url`    | ""                       | Ldap server |
| `saslauthd_ldap_userdn` | ""                       | Ldap user DN |
| `smtpd_tls_cert_file`   | ""                       | Path to ssl cert file |
| `smtpd_tls_key_file:`   | ""                       | path to ssl key file |

## Examples

	---
	- hosts: apps_smtp
	  become: yes
	  become_method: sudo
	  gather_facts: yes
	  roles:
	    - role: ansible-apps_smtp
	  environment: 
	    http_proxy: "{{ http_proxy }}"
	    https_proxy: "{{ https_proxy }}"
	    no_proxy: "{{ no_proxy }}

## License

This project is licensed under Apache License. See [LICENSE](/LICENSE) for more details.
