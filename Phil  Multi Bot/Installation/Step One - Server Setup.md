Before starting the installation process make sure you read through [the prerequisites](/c/faxstore/prerequisites).


If it isn't already, make sure you have an [A Record](https://support.dnsimple.com/articles/a-record) pointed to your server IP doe the domain you wish to use.

---

## Install a LEMN Stack

A LEMN stack is a group of programs that will be the core operators for our website.
**L**  inux
**E**  ngine-X (but written as Nginx)
**M**  ySQL Database
**N**  odeJs

First off we want to Login to a [terminal](https://en.wikipedia.org/wiki/Command-line_interface), I recommend using [Termius](https://termius.com) as it's very user friendly and easy to navigate (download via their site or Microsoft Store).


#### Installing Nginx

Once you have logged into the terminal we want to start by updating our package index and then installing [Nginix](https://www.nginx.com)

*Tip: Enter one command at a time when using a command-line interface.*

```
sudo apt update
sudo apt install nginx
```

You will be prompted to press `Y` to install Nginx, do this.

Once Nginx is installed you should be able to navigate to your servers IP and you should be presented with the below page.

`http://server_IP`

![nginx page](https://assets.digitalocean.com/articles/lemp_ubuntu_1604/nginx_default.png)

If you see the above image you have successfully installed Nginx.


#### Installing MySQL

Now we can move onto MySQL. MySQL is a type of database which is widely used around the world.

To install MySQL run the below commands
```
sudo apt install mysql-server

sudo mysql_secure_installation
```
Again, if prompted press `Y` to install MySQL.


Now that MySQL is installed and running we want to change the password for our MySQL server (this is a separate password to the one we just entered in the setup).

Login to MySQL using the `mysql` command.

```
sudo mysql
```

Next, we want to change our SQL password. Be sure to change `password` in the below command.

```sql
ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'password';
```

Once, you have entered this command you want to refresh MySQLs permissions using the `FLUSH` command.

```sql
FLUSH PRIVILEGES;
```

Now type `exit` and press enter to leave MySQL.

```js
// Note: After changing our root password we can no longer just use the mysql command. Now you will have to use the below command to enter MySQL

mysql -u root -p

// After entering this you will be prompted for a password
```

Now our database system is set up and installed.


#### Installing Node.Js

Node.Js is a very robust and popular framework for JavaScript. We will want to install Node.Js on our system as FaxStore indeed requires it. For this we will use Node Package Manager (NVM)

Install NVM along with Node.Js onto our system
```bash
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.1/install.sh | bash

nvm install 16.13.2
```


#### Certbot (SSL)

Lastly, we want to install [Certbot](https://certbot.eff.org). This allows us to automatically issue and install SSL certificates on our domain which makes user connections secure.

To install Certbot run the below command.

```bash
sudo apt install certbot python3-certbot-nginx
```

---

**Great job!** You've finished installing the software requirements!
