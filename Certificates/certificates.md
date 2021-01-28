# Certificates
## Useful tools
* openssl
## Basics
X.509 certificates are specified in ASN.1 with the "DER" encoding rules.
## View certs on server
`openssl s_client -showcerts -connect 10.10.10.1:443 -servername test.server.dev`
