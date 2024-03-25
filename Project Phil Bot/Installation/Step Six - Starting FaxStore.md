Well, congratulations you've made it to the last step in the installation guide. This article is an easy one.

First off we want to create a license key at [license.faxes.zone](https://license.faxes.zone). Once you create a license key copy the key and place it in your config file.

After that,

Create a [screen session](/c/knowledgebase/screen) with `screen -S faxstore`

Once in your screen session we will want to navigate to the directory of our application. Use `cd /home/faxstore`

We have one more important step before we start FaxStore... We must install the node modules.
Run the install command

```
npm install
```
This installs the required packages that help run FaxStore.

Now, it's time to start FaxStore. Use the basic start command with
```
node .
```

*Only use the below method if above causes a crash.*

If you're finding yourself with issues regarding FaxStore crashing for being 'out of memory' you may want to consider setting a RAM allocation for FaxStore when starting.

```sh
node . --max-old-space-size=1024 # increase to 1gb
node . --max-old-space-size=2048 # increase to 2gb
node . --max-old-space-size=3072 # increase to 3gb
node . --max-old-space-size=4096 # increase to 4gb
node . --max-old-space-size=5120 # increase to 5gb
node . --max-old-space-size=6144 # increase to 6gb
node . --max-old-space-size=7168 # increase to 7gb
node . --max-old-space-size=8192 # increase to 8gb
```

---

**Congratulations!**
FaxStore is now up and running. Please be sure to check out the guide on [using screen sessions](/c/knowledgebase/screen) for a more detailed guide on how you can control FaxStore.
