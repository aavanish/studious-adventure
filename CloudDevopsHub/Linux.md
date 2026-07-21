# SSH keygen 

To generate the private and public key, we can use command
```
ssh-keygen
```
This will create the file in /root/.ssh folder (private key and public key). We can further cat the file and copy public key whenever reqested by team for access generation.

# Add User Commands
```
adduser <username>

passwd : change password of the user

userdel : delete user

addgroup <grpname>

getent group

usermod -a -G group usermane : adds user to the group

delgroup

chage : change user password expiry information
```
Relevant files:

| Location |  Use |
|--------|--------|
| /etc/passwd |  user information |
| /etc/shadow |  encrypted passwd |
| /etc/group  |  group information |
| /etc/sudoers | configurations for sudo |


# System Admin and Monitoring

| Command |  Use |
|--------|--------|
| uname -a  | shows kernel name, kernel release, kernel version |
| sudo | Run a command as a root user |
| top | Display processor activity of system |
| uptime | Show how long system is running |
| wget | Download file from network |
| free | Show memory status |
| last | Display user's activity in the system |
| ps | Display about processes running on the system |
| df / df -h (mb) | Display filesystem information |
| du | Display usage |
| ping | Check connection by sending packet, to test packet |
| who | Same as w but doesn't show current process |
| locate | search patten locate *. txt |
| mkdir myfiles ; touch myfiles/{a.txt,b.txt,c.txt} | make directory , create an empty file |
| tar -cvf allfiles.tar myfiles - Zip/tar all files |    Create verbose file |
| tar -xvf allfiles.tar untar | extract verbose file |

tar operation - The Linux "tar" stands for tape archive, which is used by a large number of
Linux/Unix system administrators to deal with tape drives backup (compressing + binding)

# Network Command

| Command |  Use |
|--------|--------|
| ifconfig | IP address and  active network interfaces |
| sudo ifconfig eth0 up | Bring active network interfaces up |
| sudo ifconfig eth0 192.168.1.101 netmask 255.255.255.0 | Assign an IP address |
| ifconfig eth0 | Verify Changes |
| dig www.xyz.com | dns related query (will get the ip addresses of the servers) |
| netstat / ss | display connection info |
| nslookup | dns reltd query |
| route ww.google.com | view, add, modify, or delete entries in the IP routing table |
| ping | to check connectivity between 2 nodes |
| hostname | displays hostname info |
| curl / wget | Download file from network |
| mtr | My Trace Route - check network connectivity, diagonise packet loss |

# Device Commands

| Command |  Use |
|--------|--------|
| lsblk | Information about block devices |
| dmesg | troubleshooting hardware and driver issues |
| cat /proc/cpuinfo | CPU Information |
| free -m |  shows memory usage -  total, used, and free memor |
| df -h |  filesystem disk space usage -h human readable |
| lshw | list hardware CPU, memory, storage, network devices, and buses |

