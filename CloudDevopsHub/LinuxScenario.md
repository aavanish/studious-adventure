# RealTime Troubleshooting in Linux

## 1. How to Check System Logs?
   
-> Location of System Logs

Most logs are stored in the/var/log/ directory.
```
cd /var/log
ls -l
```

### Common Log Files
| File Purpose | INFRA LOG |
|--------------|------------|
| /var/log/syslog or /var/log/messages | General system log |
|/var/log/auth.log | Authentication logs (login, sudo, etc.) |
|/var/log/dmesg |  Boot and hardware-r~lated messages |
|/var/log/kern.log | Kernel logs |
|/var/log/boot.log | Boot messages |
|/var/log/faillog | Failed login attempts |
|/var/log/secure |  Security-related messages (RedHat/CentOS) |

**Zombie process** - When a parent process is end but a child process is still running which is usually runs inside the parent process.

**Cache** - A temporary memory stored. A buffer memory stored for faster load if requested. REDIS stores cache memory

**Swap Memory** - a memory that can be used beyond limit. whenever you face 100% utilaisation then swap memory could be used.

--------------------------------------------------------------------
## 2. Check System Performance
--> Commands
```
top      Real time process and resource usage
htop     improved version of top
vmstat   system performance summary (Displays CPU, memory and IO stats every second)
```
--------------------------------------------------------------------
## 3. How to Check & Fix Disk Problems?
```
df -h
```
--------------------------------------------------------------------
## 4. How Fix File Permission Issues?
Try to understand the permissons **drwxr-xr-x**
```
ls -l      long list
chmod 700 file.txt
```
--------------------------------------------------------------------
## 5. Fix Services Issues?
first restart and check system process
```
systemctl start/status/refresh/stop nginx
systemctl start/status/refresh/stop docker
systemctl start/status/refresh/stop jenkins
systemctl start/status/refresh/stop httpd  (for Apache)
systemctl start/status/refresh/stop tomcat
```
The services are kept in /etc/apt 

--------------------------------------------------------------------
## 6. How to Debug Errors?
   
you can check the file syslog
```
cat /var/log/syslog
dmseg | tail -20
```
--------------------------------------------------------------------
## 7. how to Find and Kill the process?

can be used when u have any zombie process running and you need to check and trace the root cause.
```
ps -aef    (to check all the running process)
ps -aef | grep nginx/docker       (to check a specific service)
```

then if you want to kill that running process. You can select the parent process here it is written as PID 439 and kill it.
```
Process      PID     PID                   Process
root         439       1  0 16:52 ?        00:00:00 nginx: master process /usr/sbin/nginx -g daemon on; master_process on;
www-data     440     439  0 16:52 ?        00:00:00 nginx: worker process
www-data     441     439  0 16:52 ?        00:00:00 nginx: worker process
www-data     445     439  0 16:52 ?        00:00:00 nginx: worker process
www-data     446     439  0 16:52 ?        00:00:00 nginx: worker process
www-data     447     439  0 16:52 ?        00:00:00 nginx: worker process
www-data     448     439  0 16:52 ?        00:00:00 nginx: worker process
www-data     449     439  0 16:52 ?        00:00:00 nginx: worker process
www-data     450     439  0 16:52 ?        00:00:00 nginx: worker process
root        5669    1105  0 20:55 pts/2    00:00:00 grep --color=auto nginx
```
Using kill -9 or kill -11 unsafely may lead to data loss or inconsistent states since cleanup is bypassed. Always prefer SIGTERM for normal shutdowns.
```
# Gracefully stop a service process
kill -15 1234

# Forcefully terminate a hung process
kill -9 1234

# Simulate crash (for testing/debugging)
kill -11 1234
```
| Command | Signal | Behavior | Deletes Service? |
|--------------|------------|--------------|------------|
| kill -9 | SIGKILL | Forceful termination, cannot be ignored | No | 
| kill -15 | SIGTERM | Graceful termination, can clean up | No |
| kill -11 | SIGSEGV | Crash process with segmentation fault | No|
--------------------------------------------------------------------
## 8. How to troubleshoot H/w related issue   (Data Center)
 ```
lsblk                     block devices information
dmesg                     boot up info details
cat /proc/cpuinfo
free -h                   free and used memory
df                        disk space details
lshw                      list hardware systeminfo
```
