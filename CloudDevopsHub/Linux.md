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
