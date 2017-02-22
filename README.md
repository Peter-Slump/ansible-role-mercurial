# Ansible role Mercurial (HG)

Version: 0.0.0

Supported OS: Ubuntu

Ansible role Mercurial (HG). It installs the web-interface for Mercurial.

- Configures Nginx to make the web interface accessible.
- Installs a tool to create users.

## Role variables

```
mercurial_user: 'hg'
mercurial_group: 'hg'
mercurial_home: '/home/hg'

mercurial_repository_path: "{{ mercurial_home }}/repos"
mercurial_web_path: "{{ mercurial_home }}/web"

mercurial_hostname: 'hg.example.com'
mercurial_fcgi_port: 9003

# Configure SSL options which are passed to the Nginx role.
mercurial_use_letsencrypt: False
mercurial_use_self_signed_ssl: False

# Salt used for hashing passwords of created users.
mercurial_salt: 'ThisIsNotVerySecure'
```

## Example
```
- hosts: all
  roles:
    - role: mercurial
      mercurial_hostname: my-host.example.com
```

## User create example
```
$ python adduser.py
```
