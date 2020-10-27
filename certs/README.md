# Generate certs

In this steps, create self-signed CA certificate and server certificate signed by the CA.

```
# generate files for CA
cfssl print-defaults config > ca-config.json
cfssl print-defaults csr > ca-csr.json

#edit ca-config.json and ca-csr.json


# generate certs for CA
cfssl gencert -initca ca-csr.json | cfssljson -bare ca -

cfssl print-defaults csr > server-csr.json

# edit server-csr.json

# generate certs for server
cfssl gencert -ca ca.pem -ca-key ca-key.pem -config ca-config.json -profile server server-csr.json | cfssljson -bare server -
```
