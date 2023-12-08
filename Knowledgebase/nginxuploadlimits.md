Have you been using Nginx and have come across this annoying message?

![nginxerror](https://faxes.zone/i/7HcEq.png)

This might just be the place you're looking for. By default NGINX comes with a rather small upload limit for mainly security and disk usage reasons. However, this is a simple to change issue for all. Follow the below steps for a quick fix on this issue.

### Open The Config File
By default there will be an NGINX config file located at

```
/etc/nginx/nginx.conf
```

Open this file via SMTP or the [nano command](https://www.howtogeek.com/howto/42980/the-beginners-guide-to-nano-the-linux-command-line-text-editor/)

### Applying The Fix
Now this file is structured in a particular way. So we can't go around placing this anywhere.

In the HTTP block (after `http {`) we want to place our line.

```
client_max_body_size 1000M; # This will increase the limit to 1GB. Measured in MB.
```

Keep note that setting it to `0` disables checking of client request body size.

(client_max_body_size 0; # Disables checking client body size)

![applythefix](https://faxes.zone/i/NWXTc.png)

Once complete save the file and close.

#### Finishing Up
Now there's one last thing to check before applying our changes.

We first want to double check our syntax to ensure we have entered the information correctly

Run this command in your terminal to check the syntax of our edits.

```
nginx -t
```
Our expected output should be all good

![termout](https://faxes.zone/i/waB64.png)

If all is well then restart NGINX to apply our changes in full

```
service nginx restart
```