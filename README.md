apache_tls
======================

Ansible Galaxy role [cesnet.apache_tls](https://galaxy.ansible.com/cesnet/apache_tls) that installs Apache HTTPD
and configures TLS (Transport Layer Security) correctly to pass the [SSLLabs Server Test](https://www.ssllabs.com/ssltest/index.html)
with A+ rating. 

Installs certificate chains for "GEANT OV RSA CA 4" and "GEANT OV ECC CA 4". 
It also enables HTTP2 protocol and cronolog for daily log rotation.

It does not set up any web sites.

Requirements
------------

-

Role Variables
--------------

- certs_dir - the directory for storing CA certs, default is /etc/ssl/localcerts 
- geant_rsa_chain_file - path to file with "GEANT OV RSA CA 4" cert chain, default "{{certs_dir}}/geant_ov_rsa_ca_4.pem"
- geant_ecc_chain_file - path to file with "TERENA SSL CA 3" cert chain, default is "{{certs_dir}}/geant_ov_ecc_ca_4.pem"

Example Playbook
----------------
```yaml
- hosts: all
  roles:
    - role: cesnet.apache_tls
      vars:
        certs_dir: /etc/apache2/ssl
```