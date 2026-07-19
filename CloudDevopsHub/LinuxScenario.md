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
--------------------------------------------------------------------
6. How to Debug Errors?
7. how to Find and Kill the process?
8. How to troubleshoot H/w related issue

