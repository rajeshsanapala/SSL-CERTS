Work flow:
+++++++++++

1. Place the certificate contents in Ansible Vault as below with certificate, private_key, csr

# Create a new vault
ansible-vault create certificate.yml

# Edit an existing vault
ansible-vault edit certificate.yml

---
ssl_certificate: 
  name: "self-signed.crt" 
  content: |  
  -----BEGIN CERTIFICATE-----
  ...
  -----END CERTIFICATE-----

ssl_private_key:
  name: "server-master.key"
  content:  |
  -----BEGIN PRIVATE KEY-----
  ...
  -----END PRIVATE KEY-----

ssl_csr:
  name: "client.csr" 
  content: |
  ---- BEGIN CSR --------
  ....
  ----- END CSR -----------


2. Verify if the certificate on the target server has expired or about to expire in 7 days
3. Read the contents of the files from the above Ansible vault & copy the required files on the target server
4. Use the copied files from ansible vault & generate a new certificate & deploy it to the server
5. Notify httpd service restart using handler.
6. Delete the 3 files copied after the certificate has been generated