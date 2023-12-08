Updating Node.Js on Ubuntu

Sometimes updating Node.Js on Ubuntu can be more on the painful side for users that are new to Linux. This causes confusion and issues when it comes to having to update software! Thankfully the process of updating Node.Js is easy with this version manager.

### NWM (Node Version Manager)
NVM is a simple command line tool to update your Node installation to any version you wish to use!

To update simply run the bellow commands!

Update the package repository

```
sudo apt update
```
Install NVM if you haven't with `curl`

```curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.4/install.sh | bash```
*You may need to restart the terminal to register the new commands.*

To verify you have installed NVM check the version with

```
nvm -v
```
Use the encouraged version of node for Project Phil products with. Note some products now require 20.5.1 instead.

```
nvm install 16.13.2
```
If you'd like to set this as your machines default node version, use the below command.

```
nvm alias default 16.13.2
```
Having Troubles?
If you're still having troubles you can run the command `nvm` to display the NVM help menu. Or join Project Phil Discord for further help.