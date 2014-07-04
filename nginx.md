Nginx Cheatsheet
================

### Installation
`sudo apt-get install nginx`

### Starting the server
`sudo service nginx start`

### Stopping the server
`sudo service nginx stop`

### Editing the nginx config file
`sudo vim /etc/nginx/nginx.conf`

### Some settings worth noting
    # Reduce the amount of info returned by Nginx
    server_tokens off;

    # Limit the file upload size
    client_max_body_size 4096K;

### Test the config file
`sudo /usr/bin/nginx -t -c /etc/nginx/nginx.conf`

### SSL Certificate

1.  Create a directory for the certificate

        mkdir /etc/nginx/ssl
        cd /etc/nginx/ssl

2.  Create the server key and the certificate signing request

    *   Create a server key with a passphrase.

        `sudo openssl genrsa -des3 -out server.key 4096`

    *   Create the certificate signing request. The most important line is **Common Name**. Enter your official domain name here. Leave the challenge password and optional company name blank. You can submit the CSR file to a Certificate Authority for signing.

        `sudo openssl req -new -key server.key -out server.csr`

    *   Limit access to the server key by setting its file permission:

        `chmod 400 server.key`

3.  Create a self-signed certificate (optional).

    `openssl x509 -req -days 365 -in server.csr -signkey server.key -out server.crt`

4.  Setting up Nginx
    
    *   Combine all chain certificates with your server certificate. Make sure that your server certificate comes first.

            cat certificate.crt GandiStandardSSLCA.pem > server.crt

    *   Create a copy of the server key. This will serve as a backup.

        `sudo cp server.key server.key.orig`

    *   Remove the passphrase from the server key. This will allow Nginx to easily use the server key without having to provide the passphrase.

        `sudo openssl rsa -in server.key.orig -out server.key`

    *   Edit the Nginx configuration file. Setup Nginx to use the SSL certificate.

            http {
                ssl_session_cache    shared:SSL:10m;
                ssl_session_timeout  10m;

                # Redirect HTTP requests to HTTPS
                server {
                    listen       80;
                    server_name  example.com
                    return       301 https://example.com$request_uri;
                }

                server {
                    listen             443 ssl;
                    server_name        example.com;
                    keepalive_timeout  70;

                    root   /usr/share/nginx/www;
                    index  index.html index.htm;

                    ssl                  on;
                    ssl_certificate      /etc/nginx/ssl/server.crt;
                    ssl_certificate_key  /etc/nginx/ssl/server.key;
                }
            }
