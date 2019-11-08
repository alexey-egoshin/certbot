###Obtaining SSL certificates

```bash
sudo docker-compose build
```

set domain name in `init-letsencrypt.sh`

file in line:

```bash
domains=(you.domain.name)
```
and
 in `docker/nginx/conf.d/default` in lines:
 
 server_name `you.domain.name`;
 
 ssl_certificate /etc/letsencrypt/live/`you.domain.name`/fullchain.pem;
 
 ssl_certificate_key /etc/letsencrypt/live/`you.domain.name`/privkey.pem;
 

Run: 
```bash
sudo ./init-letsencrypt.sh

sudo docker-compose up -d

sudo sh -c "cp -LR docker/certbot/conf/live/* /etc/nginx/ssl/"
```

Obtained certificates will be in `/etc/nginx/ssl/you.domain.name`

folder
 

 
 
 
 
