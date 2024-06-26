Welcome to the new simplified Phil Bot install. Installing Phil Bot is now as easy as running one command to install it all!

All software requirments and packages install easily now.

:::danger
This file **MUST** be run using the `root` user account.
:::

1. Create an A record to direct your domain DNS to your machines IP.
2. Install Phil Bot files to `/home/philbot`.
3. Run the below command to start the installation.

```sh
bash /home/philbot/install.sh
```

Now Phil Bot will install; nginx, mysql-server, certbot, python3-certbot-nginx, Node.Js, and NPM.

Phil Bot will also launch a screen session for you and give you the prompt to start.

4. Phil Bot will start and prompt you through a brand new setup process.

*This is a beta feature, so give us [feedback](https://bugs.projectphil.co.uk/projects/philbot/add?t=feedback) on your experience with this simplified install.*
*[Improve this page](https://github.com/ProjectPhil/Documentation/tree/main/philbot)*

:::info
If you've completed this step, you don't have to go through the other install steps.
:::
