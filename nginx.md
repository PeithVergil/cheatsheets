Nginx Cheatsheet
================

### Installation
`sudo apt-get install nginx`

### Starting the server
`sudo service nginx start`

### Stopping the server
`sudo service nginx stop`

### SSL Certificate

1.  Create a directory for the certificate

        mkdir /etc/ssl/certs
        cd /etc/ssl/certs

2.  Create the server key and the certificate signing request

    *   Create a server key with a passphrase.

        `openssl genrsa -des3 -out server.key 1024`

    *   Rename the server key with a passphrase.

        `mv server.key server.key.orig`

    *   Create a server key without a passphrase.

        `openssl rsa -in server.key.orig -out server.key`

    *   Create the certificate signing request. You can submit the CSR file to a CA for signing.

        `openssl req -new -key server.key -out server.csr`

3.  Create a self-signed certificate

    `openssl x509 -req -days 365 -in server.csr -signkey server.key -out server.crt`

    ### Setup Nginx to use the SSL certificate

        server {
            listen 443;
            server_name example.com;

            root /usr/share/nginx/www;
            index index.html index.htm;

            ssl on;
            ssl_certificate /etc/nginx/ssl/server.crt;
            ssl_certificate_key /etc/nginx/ssl/server.key;
        }