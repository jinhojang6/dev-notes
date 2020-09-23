## HTTPS
Hypertext Transfer Protocol Secure (HTTPS) is an extension of the Hypertext Transfer Protocol (HTTP). It is used for secure communication over a computer network, and is widely used on the Internet. In HTTPS, the communication protocol is encrypted using Transport Layer Security (TLS) or, formerly, its predecessor, Secure Sockets Layer (SSL). The protocol is therefore also referred to as HTTP over TLS, or HTTP over SSL.

- https://en.wikipedia.org/wiki/HTTPS

<br />

## Extract crt, key, and rsa files from a pfx file

```
crt
openssl pkcs12 -in {filename.pfx} -clcerts -nokeys -out {filename.crt}

key
openssl pkcs12 -in {filename.pfx} -nocerts -out {filename.key}

rsa
openssl pkcs12 -in {filename.pfx} -nocerts -nodes -out {filename.rsa}
```

<br/>

## Let's Encrypt
A nonprofit Certificate Authority providing TLS certificates

- https://letsencrypt.org/

<br />

## Let's Encrypt HTTPS tutorial (Ubuntu 18.04)
Setup
```
sudo wget http://nginx.org/keys/nginx_signing.key
sudo apt-key add nginx_signing.key
cd /etc/apt
sudo vim sources.list
```

Add the 2 lines below at the bottom
```
deb http://nginx.org/packages/ubuntu xenial nginx
deb-src http://nginx.org/packages/ubuntu xenial nginx
```

Start NGINX
```
sudo apt-get update
sudo apt-get install nginx
sudo service nginx start
```

Install Let's Encrypt
```
sudo apt-get update
sudo apt-get install software-properties-common
sudo add-apt-repository ppa:certbot/certbot
sudo apt-get update
sudo apt-get install python-certbot-nginx
```

Change server name
```
sudo vim /etc/nginx/conf.d/default.conf
# replace "localhost" with your domain (e.g., *.jinho.com)
```

Run certbot
``` 
sudo certbot --authenticator standalone --installer nginx -d {domain} --pre-hook "service nginx stop" --post-hook "service nginx start"
```

- [Setting Up An HTTPS Server With Node, Amazon EC2, NGINX And Let’s Encrypt](https://blog.cloudboost.io/setting-up-an-https-sever-with-node-amazon-ec2-nginx-and-lets-encrypt-46f869159469)
- [Unauthorized Detail: Invalid response from](https://community.letsencrypt.org/t/type-unauthorized-detail-invalid-response-from/36183)
- [Certbox: Could not automatically find a matching server block](https://community.letsencrypt.org/t/certbox-could-not-automatically-find-a-matching-server-block/105265)

## Let's Encrypt auto renewal
Check expiration date
```
echo | openssl s_client -connect <you server here>:443 2>/dev/null | openssl x509 -noout -dates
```

Renew
```
./letsencrypt-auto renew
sudo crontab -e
```

- [Nginx auto renewal](https://community.letsencrypt.org/t/nginx-auto-renewal/30894)
- [Install Let's Encrypt to Create SSL Certificates](https://www.linode.com/docs/security/ssl/install-lets-encrypt-to-create-ssl-certificates/)

<br />
