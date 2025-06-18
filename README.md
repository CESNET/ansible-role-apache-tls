apache_tls
======================

Ansible Galaxy role [cesnet.apache_tls](https://galaxy.ansible.com/cesnet/apache_tls) that installs Apache HTTPD
and configures TLS (Transport Layer Security) correctly to pass the [SSLLabs Server Test](https://www.ssllabs.com/ssltest/index.html)
with A+ rating. 

It does not set up any web sites.

Requirements
------------

-

Role Variables
--------------

- apache_tls_ocsp_stapling - whether to enable OCSP stapling, default is false

Example Playbook
----------------
```yaml
- hosts: all
  roles:
    - role: cesnet.apache_tls
      vars:
        apache_tls_ocsp_stapling: true
```
