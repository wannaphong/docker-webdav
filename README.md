# Servidor webdav partiendo de debian-testing

##  Clonar el repositorio

```
git clone https://github.com/wannaphong/docker-nginx-webdav.git
```
how to run

```
docker run -d \
    -v /home/webdav:/media \
    -v /etc/letsencrypt/live/example.com/fullchain.pem:/etc/nginx/ssl/fullchain.pem \
    -v /etc/letsencrypt/live/example.com/privkey.pem:/etc/nginx/ssl/privkey.pem \
    -e USERNAME=admin \
    -e PASSWORD=admin \
    -p 8765:443 \
    --restart=unless-stopped \
    --name=webdav \
    ghcr.io/wannaphong/docker-webdav:v0.3.2
```

You can gen letsencrypt from

```
certbot certonly --standalone -d example.com
```

and renew 

```
certbot renew
```

every 30 days
