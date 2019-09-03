apache_tls
======================

Ansible Galaxy role [cesnet.apache_tls](https://galaxy.ansible.com/cesnet/apache_tls) that installs Apache HTTPD
and configures TLS (Transport Layer Security) correctly to pass the [SSLLabs Server Test](https://www.ssllabs.com/ssltest/index.html)
with A+ rating. 

Installs certificate chains for "TERENA SSL CA 3" and "TERENA SSL High Assurance CA 3". 
It also enables HTTP2 protocol and cronolog for daily log rotation.

It does not set up any web sites.

Requirements
------------

-

Role Variables
--------------

- certs_dir - the directory for storing CA certs, default is /etc/ssl/localcerts 
- terena_ev_chain_file - path to file with "TERENA SSL High Assurance CA 3" cert chain, default "{{certs_dir}}/terena_ssl_high_assurance_ca_3.pem"
- terena_dv_chain_file - path to file with "TERENA SSL CA 3" cert chain, default is "{{certs_dir}}/terena_ssl_ca_3.pem"

Example Playbook
----------------
```yaml
- hosts: all
  roles:
    - role: cesnet.apache_tls
      vars:
        certs_dir: /etc/apache2/ssl
```