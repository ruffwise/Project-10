# Project-10: LOAD BALANCER SOLUTION WITH NGINX AND SSL/TLS

### configure Nginx as a load balancer

`sudo apt update`

`sudo apt install nginx`

### edit nginx configuration file

![](/images/nginx-conf.png)

![](/images/log-in.png)

### install certbot and request ssl certificate

`sudo snap install --classic certbot`

`sudo ln -s /snap/bin/certbot /usr/bin/certbot`

`sudo certbot --nginx`

![](/images/https.png)

### test certificate renewal

`sudo certbot renew --dry-run`
![](/images/test-renewal.png)

### schedule certificate renewal job

`crontab -e`

`* */12 * * *   root /usr/bin/certbot renew > /dev/null 2>&1`
