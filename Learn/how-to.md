

# How to start Nginx

To start nginx, run the executable file.

```
nginx

```

Or

```
[sudo ]service nginx start

```

# How to see the Nginx status


```
[sudo]service nginx status

```

# How to stop Nginx

** To fast shutdown **

```
nginx -s stop

```
or

```
[sudo]service nginx stop

```

or

```
ps -aux | grep "nginx: master" //to see the pid of the master process
kill -9 <master-process-id>

```


** To graceful shutdown. **

this will stop nginx processes with waiting for the worker processes to finish serving current requests. (This command should be executed under the same user that started nginx.)

```
nginx -s quit

```

or

```
ps -aux | grep "nginx: master" //to see the pid of the master process
kill -s QUIT <master-process-id>

```

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
