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

ifconfig : 

dig www.xyz.com : dns related query (will get the ip address of the servers)

netstat / ss : display connection info

nslookup : dns reltd query

route ww.google.com :

ping : to check connectivity between 2 nodes

hostname : 

curl / wget :

mtr :

# Device Commands

lsblk

dmseg

cat /proc/cpuinfo

free -m

df -h

lshw

