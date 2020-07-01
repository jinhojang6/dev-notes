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
