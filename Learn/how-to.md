
# How to enable charset HTTP-header in Nginx

Go to the folder of your nginx configuration file:


```
cd /etc/nginx/

```

Open your nginx.conf, enter:


```
 vi nginx.conf
 
```

Append/modify the following directive in http, server, or location:


```
charset UTF-8;

```
Save and close the file. Reload the nginx web server, enter:


```
[sudo] service nginx reload

```
