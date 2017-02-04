
### Root inside Location Block

This works. Putting root inside of a location block will work and it’s perfectly valid. What’s wrong is when you start adding location blocks. If you add a root to every location block then a location block that isn’t matched will have no root. Therefore, it is important that a root directive occur prior to your location blocks, which can then override this directive if they need to. Let’s look at a good configuration.


BAD:


``` 

server {
    server_name www.example.com;
    location / {
        root /var/www/nginx-default/;
        # [...]
      }
    location /foo {
        root /var/www/nginx-default/;
        # [...]
    }
    location /bar {
        root /some/other/place;
        # [...]
    }
}


```

GOOD:


```
server {
    server_name www.example.com;
    root /var/www/nginx-default/;
    location / {
        # [...]
    }
    location /foo {
        # [...]
    }
    location /bar {
        root /some/other/place;
        # [...]
    }
}

```