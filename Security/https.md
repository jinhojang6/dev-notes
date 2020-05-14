## HTTPS
Hypertext Transfer Protocol Secure (HTTPS) is an extension of the Hypertext Transfer Protocol (HTTP). It is used for secure communication over a computer network, and is widely used on the Internet. In HTTPS, the communication protocol is encrypted using Transport Layer Security (TLS) or, formerly, its predecessor, Secure Sockets Layer (SSL). The protocol is therefore also referred to as HTTP over TLS, or HTTP over SSL.

- https://en.wikipedia.org/wiki/HTTPS

<br />

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


- [Reference 1](https://blog.cloudboost.io/setting-up-an-https-sever-with-node-amazon-ec2-nginx-and-lets-encrypt-46f869159469)
- [Reference 2](https://community.letsencrypt.org/t/type-unauthorized-detail-invalid-response-from/36183)
- [Reference 3](https://community.letsencrypt.org/t/certbox-could-not-automatically-find-a-matching-server-block/105265)
