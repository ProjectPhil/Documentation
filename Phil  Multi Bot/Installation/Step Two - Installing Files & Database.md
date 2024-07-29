Welcome to the file and database installation section! If you haven't already view [Step One - Server Setup](/c/faxstore/stepone).

---

As FaxStore uses Node.Js we want to use a proxy to direct users to the application through a manipulation method.

If you don't have a SFTP viewer take a look at [WinSCP](https://winscp.net/eng/index.php)


#### Nginx Configuration

Using a SFTP viewer navigate to `/etc/nginx/sites-available/default`. This is the Nginx site configuration. Delete the contents of the default file if you haven't made changes to it before.

Replace the contents with the below and change the `port` and `domain` as instructed.

```sh
server {
    
  server_name example.com; # Change domain to your domain
    
  location / {
    proxy_pass http://localhost:3000; # Change the port if needed.
    proxy_http_version 1.1;
    proxy_set_header Upgrade $http_upgrade;
    proxy_set_header Connection 'upgrade';
    proxy_set_header Host $host;
    proxy_cache_bypass $http_upgrade;
    proxy_set_header X-Real-IP $remote_addr;
  }    
    error_page 502 /502.html;
    location = /502.html {
        root  /home/faxstore/public;
    }
}
```

Once you have made your changes save the file and restart Nginx.

```
sudo systemctl restart nginx
```


#### Issue SSL Certificate

To issue our SSL certificate we want to run the below command and replace the domain name to ours.

```sh
sudo certbot --nginx -d example.com
```

You may be asked for some details like an email (this doesn't get used publicly).

When directed for a redirect method select the `2` option.


Now our certificate is issued we want to make sure it renews itself. Run the renew command to do so.

```sh
sudo certbot renew --dry-run
```

#### Installing FaxStore Files

This might be the easiest step in the whole guide.

Using a SFTP application like WinSCP copy and paste the contents of our download to the `/home` directory.

We want to end location to be `/home/faxstore` so create a new directory if needed.

![winscpview](https://faxes.zone/i/hBJFF.png)


#### Installing The Database

Now, back to the harder stuff, it's time to install the MySQL database for FaxStore.

Login to our MySQL server using the `mysql -u root -p` command and enter your password.

Next all we need to do once logged in is run the below command.


```sql
source /home/faxstore/installme.sql
```


#### Discord Application

FaxStore comes with a built in Discord bot, this is optional in the configuration file. It includes logging and other enhanced features.

We will want to create a Discord Application in the [Discord Developer Portal](https://discord.com/developers/applications)

Create an application and add a bot profile.

![discordappcreate](https://faxes.zone/i/RUjze.gif)

In the Bot tab enable all gateway intents.

After that, invite the Discord bot to your guild, replacing `CLIENT_ID_HERE` with your bot ID.
```
https://discord.com/oauth2/authorize?client_id=CLIENT_ID_HERE&permissions=8&scope=bot%20applications.commands
```
