To search for processes using a specific port run the following commands. This can be useful if you need to end/stop a service running on a specific port. To do this follow the below instructions.

Run the `lsof` command below, change the port if needed to what you need.

```
lsof -i tcp:3000
```

You'll get the results listed like this.

Look under the PID column and copy that process ID into the below command to stop the process.

```
kill 9506
```
This command ends/stops the process so it is no longer running.