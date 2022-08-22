# Become a Certificate Authority - OpenSSL Windows

## Generate private key (First time only!)
`openssl genrsa -des3 -out ca.key 2048`
### Generate root certificate
`openssl req -x509 -new -nodes -key ca.key -sha256 -days 825 -out ca.pem`

## Create CA-signed certs
### Generate a private key
`openssl genrsa -out $NAME/cert.key 2048`

### Create a certificate-signing request
`openssl req -new -key $NAME/cert.key -out $NAME/cert.csr`
### Create file = $NAME/cert.txt

```
authorityKeyIdentifier=keyid,issuer
basicConstraints=CA:FALSE
keyUsage = digitalSignature, nonRepudiation, keyEncipherment, dataEncipherment
subjectAltName = @alt_names
[alt_names]
DNS.1 = $DOMAIN
```

# Create the signed certificate
 `openssl x509 -req -in $NAME/cert.csr -CA ca.pem -CAkey ca.key -CAcreateserial -out $NAME/cert.crt -days 825 -sha256 -extfile $NAME/cert.txt`
