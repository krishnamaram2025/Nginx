* Step 1: Login to nginx server
  
* Step 2: Nginx installation and Set Up
```
sudo yum install nginx -y
```
* Step 3: Modify Nginx config
```
vi /etc/nginx/nginx.conf
server {
        listen       80;
        listen       [::]:80;
        server_name  34.232.68.3;
       location / {
        root         /usr/share/nginx/html/;
        index  index.html index.htm;
        }
```
* Step 4: To Fix the Forbidden issue
```
sudo setsebool -P httpd_enable_homedirs 1
sudo setenforce 0
sudo systemctl restart nginx
sudo systemctl daemon-reload
```
