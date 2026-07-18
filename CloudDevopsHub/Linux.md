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

/etc/passwd   user information

/etc/shadow   encrypted passwd

/etc/group    group information

/etc/sudoers  configurations for sudo


# System Admin and Monitoring

uname -a   - shows kernel name, kernel release, kernel version

sudo - Run a command as a root user

top - Display processor activity of system

uptime - Show how long system is running

wget - Download file from network

free - Show memory status

last - Display user's activity in the system

ps - Display about processes running on the system

df / df -h (mb)- Display filesystem information

du - Display usage

ping - Check connection by sending packet test packet

who - Same as w but doesn't show current process

locate - search patten locate *. txt

mkdir myfiles ; touch myfiles/{a.txt,b.txt,c.txt}

tar operation - The Linux "tar" stands for tape archive, which is used by a large number of
Linux/Unix system administrators to deal with tape drives backup (compressing + binding)


tar -cvf allfiles.tar myfiles - Zip/tar all files     (Create verbose file)
 
tar -xvf allfiles.tar  - untar  (extract verbose file)


