  By default, the configuration file is named nginx.conf and placed in the directory /usr/local/nginx/conf, **/etc/nginx **, or /usr/local/etc/nginx.

**Changes made in the configuration file will not be applied until the command to reload configuration is sent to nginx or it is restarted **.

Once the master process receives the signal to reload configuration, it **checks the syntax validity of the new configuration file **  and tries to apply the configuration provided in it. If this is a success, the master process starts new worker processes and sends messages to old worker processes, requesting them to shut down. Otherwise, the master process rolls back the changes and continues to work with the old configuration. Old worker processes, receiving a command to shut down, stop accepting new connections and continue to service current requests until all such requests are serviced. After that, the old worker processes exit.


# Resources

[Config pitfalls from nginx.com](https://www.nginx.com/resources/wiki/start/topics/tutorials/config_pitfalls/)
