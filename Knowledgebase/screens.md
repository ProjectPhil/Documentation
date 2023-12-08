### Introduction
Screen is a console application that allows you to use multiple terminal sessions within one window. The program operates within a shell session and acts as a container and manager for other terminal sessions, similar to how a window manager manages windows.

### Installation
```
sudo apt-get update
sudo apt-get install screen
```
### Basic Usage
Although running the `screen` command will create you a new screen session you may be looking for more of a customised environment to easily identify and control your screen sessions.

Here is a list of quick and easy commands along with keyboard short cuts;

```screen -S name
// This creates a screen session under the name you pick. Once created it will seem like it opens a new terminal for you. From there you run the cd and node commands.


screen -r -d name
// This reconnects you to a screen session that has already been created.


screen -ls
// Lists all active screen sessions on the machine.


CTRL + A + D
// This disconnects you from a screen session and keeps it running. It will say it has 'detached'.


CTRL + D
// This terminates the screen session and closes it for good
```
