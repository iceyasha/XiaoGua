## Nginx

安装:apt-get install ngnix

启动命令:service nginx start

终止命令: nginx -s stop

默认配置文件:/etc/nginx/nginx.conf

引入配置文件:/etc/nginx/sites-enabled/*

> 可以将我们的web配置放在这个目录下

例子：
```python
server {
    server_name localhost;你的域
    名
    listen 80 default_server;
    listen [::]:80 default_server ipv6only=on;

    root /usr/share/nginx/html;默认路径，设置为你的web目录

    location / {
    proxy_pass http://127.0.0.1:3000; web运行的host及port
    }
}
```
