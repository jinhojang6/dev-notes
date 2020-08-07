## NGINX

- [Documentation](https://www.nginx.com/)

- [Setting up with Django, Gunicorn, Postgres and Ubuntu](https://www.digitalocean.com/community/tutorials/how-to-set-up-django-with-postgres-nginx-and-gunicorn-on-ubuntu-16-04)

- [NGINX + React + Docker](https://medium.com/swlh/dockerizing-a-react-application-with-docker-and-nginx-19e88ef8e99a)

<br/>

## NGINX Port forwarding
```
server {
    listen 80;
    server_name example.com;

    location / {
        proxy_set_header   X-Forwarded-For $remote_addr;
        proxy_set_header   Host $http_host;
        proxy_pass         "http://127.0.0.1:8080";
    }
}
```
- Need to restart the NGINX service
- https://stackoverflow.com/questions/24861311/forwarding-port-80-to-8080-using-nginx

<br/>

## Troubleshooting

1. Address already in use
```
nginx: [emerg] bind() to 0.0.0.0:443 failed (98: Address already in use)
nginx: [emerg] bind() to [::]:443 failed (98: Address already in use)
```

- sudo fuser -k 80/tcp >> sudo service nginx start

<br/>


## Reverse proxy

An Nginx HTTPS reverse proxy is an intermediary proxy service which takes a client request, passes it on to one or more servers, and subsequently delivers the server’s response back to the client.

- Load Balancing: A Nginx reverse proxy can perform load balancing which helps distribute client requests evenly across backend servers. It also improves redundancy as if one server goes down, the reverse proxy will simply reroute requests to a different server according to the routing policy.

- Increased Security: A Nginx reverse proxy also acts as a line of defense for your backend servers. Configuring a reverse proxy ensures that the identity of your backend servers remains unknown.

- Better Performance: Nginx has been known to perform better in delivering static content file and analyse URLs
Easy Logging and Auditing: Since there is only one single point of access when a Nginx reverse proxy is implemented, this makes logging and auditing much simpler.

- Encrypted Connection By encrypting the connection between the client and the Nginx reverse Proxy with TLS, users profit from a encrypted and securized HTTPS connection, protecting their data.

- [How to Configure a Nginx HTTPs Reverse Proxy on Ubuntu Bionic](https://www.scaleway.com/en/docs/how-to-configure-nginx-reverse-proxy/#:~:text=Nginx%20HTTPS%20Reverse%20Proxy%20Overview,response%20back%20to%20the%20client.)
