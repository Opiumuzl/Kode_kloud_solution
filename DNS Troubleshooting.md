The system admins team of xFusionCorp Industries has noticed intermittent issues with DNS resolution in several apps .
App Server 2 in Stratos Datacenter is having some DNS resolution issues, so we want to add some additional DNS nameservers on this server.

- As a temporary fix we have decided to go with Google public DNS (ipv4). Please make appropriate changes on this server.

### First step we need to connect on app server and login to root:
```
thor@jump_host ~$ ssh steve@stapp02
The authenticity of host 'stapp02 (172.16.238.11)' can't be established.
ECDSA key fingerprint is SHA256:BEmbndWZwybHvgohbP2hOAD0j2ErgvbEi3IpLZuaOKU.
ECDSA key fingerprint is MD5:27:54:d2:2f:14:bf:27:b6:4a:70:ac:a7:34:1d:c2:cb.
Are you sure you want to continue connecting (yes/no)? yes
Warning: Permanently added 'stapp02,172.16.238.11' (ECDSA) to the list of known hosts.

steve@stapp02's password:

[steve@stapp02 ~]$ sudo su -
 We trust you have received the usual lecture from the local System
Administrator. It usually boils down to these three things:
    #1) Respect the privacy of others.
    #2) Think before you type.
    #3) With great power comes great responsibility.

 [sudo] password for steve:

[root@stapp02 ~]#
```
### Now we nedd add in /etc/resolv.conf row `nameserver 8.8.8.8`.
[root@stapp02 ~]#vi /etc/resolv.conf

>[!tip]
>   
>   search stratos.xfusioncorp.com\
>   nameserver 127.0.0.11\
>   nameserver 8.8.8.8\
>   options ndots:0
### After that, check and complete the task.
