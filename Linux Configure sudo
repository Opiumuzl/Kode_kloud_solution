We have some users on all app servers in `Stratos Datacenter`.
Some of them have been assigned some new roles and responsibilities, therefore their users need to be upgraded with sudo access so that they can perform admin level tasks.  

a. Provide sudo access to user `mariyam` on all app servers.  
b. Make sure you have set up password-less sudo for the user.

# First step we need to connect on first app server and login to root:
```sh
thor@jump_host ~$ ssh tony@stapp01
The authenticity of host 'stapp01 (172.16.238.10)' can't be established.
ECDSA key fingerprint is SHA256:BEmbndWZwybHvgohbP2hOAD0j2ErgvbEi3IpLZuaOKU.
ECDSA key fingerprint is MD5:27:54:d2:2f:14:bf:27:b6:4a:70:ac:a7:34:1d:c2:cb.
Are you sure you want to continue connecting (yes/no)? yes
Warning: Permanently added 'stapp01,172.16.238.10' (ECDSA) to the list of known hosts.

tony@stapp01's password:

[tony@stapp01 ~]$ sudo su -
 We trust you have received the usual lecture from the local System
Administrator. It usually boils down to these three things:
    #1) Respect the privacy of others.
    #2) Think before you type.
    #3) With great power comes great responsibility.

 [sudo] password for tony:

[root@stapp01 ~]#
```
# Now we need change /etc/sudoers. find in this file row "root ALL=(ALL)       ALL" and add to next row:
```
mariyam ALL = (ALL) NOPASSWD: ALL
```
# So we added a specific user to the sudo group with disabled password request for his actions.
# Now we need to repeat the same thing on the remaining servers (stapp02 and stapp03).
# After that, check and complete the task.
