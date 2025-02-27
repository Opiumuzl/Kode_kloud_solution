As per details shared by the development team, the new application release has some dependencies on the back end.
There are some packages/services that need to be installed on all app servers under `Stratos Datacenter`. As per requirements please perform the following steps:  
- a: Install `cups` package on all the application servers.  
- b: Once installed, make sure it is enabled to start during boot.

First step we need to connect on first app server and login to root:
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
# next step we need to install `cups` package:
```sh
[root@stapp01 ~]#yum install -y cups
.....installing.....
```
# next step we need to enable to start during boot:
```sh
[root@stapp01 ~]#systemctl start cups
[root@stapp01 ~]#systemctl enable cups
# and check status `cups`
[root@stapp01 ~]#systemctl status cups


# Now we need to repeat the same thing on the remaining servers (stapp02 and stapp03).
# After that, check and complete the task.
