# nginx部署

#### 安装 nginx
```
$ sudo apt-get install nginx
```

#### 启动 nginx
```
$ sudo /etc/init.d/nginx start
```

#### 安装 Node
```
$ sudo apt-get update
$ curl -sL https://deb.nodesource.com/setup_0.12 | sudo bash -
$ sudo apt-get install -y nodejs
```

#### 安装 Express(可选)
```
$ npm install express-generator -g
$ express myapp
$ cd myapp && npm install
$ DEBUG=myapp:* ./bin/www
```

#### 安装 pm2
```
$ sudo npm install -g pm2
$ pm2 start bin/www
$ pm2 startup
# sudo env PATH=$PATH:/usr/local/bin pm2 startup ubuntu -u daniel
```

#### 配置 nginx
```
$ cd /etc/nginx/sites-available && cp default example.com
$ sudo ln -s /etc/nginx/sites-available/example.com /etc/nginx/sites-enabled/
$ sudo rm /etc/nginx/sites-enabled/default
$ cd /etc/nginx/sites-available && sudo vi example.com
// root /srv/www/example.com/html;
// index index.html index.htm;
```

edit example.com

```
server {
  listen 80 default_server;
  listen [::]:80 default_server;

  server_name example.com www.example.com;

  location / {
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header Host $http_host;
        proxy_set_header X-NginX-Proxy true;
        proxy_pass http://127.0.0.1:3000/;
        proxy_redirect off;
        proxy_http_version 1.1;
        proxy_set_header Upgrade $http_upgrade;
        proxy_set_header Connection "upgrade";

        proxy_redirect off;
        proxy_set_header   X-Forwarded-Proto $scheme;
        proxy_cache off;
        proxy_cache_key sfs$request_uri$scheme;
    }
}
```

restart nginx

```
$ sudo /etc/init.d/nginx restart
```
