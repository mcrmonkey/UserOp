UserOp
======

This is a script intended to make basic user administration on a samba server a little easier.

The script
----------

The script is basically a wrapper for the "useradd" "passwd" and "smbpasswd" utilities
with the intention of making addition, removal and changes of user passwords simple

The script is written for use with bash and was orginally designed to be run with sudo, eg: 

```
sudo userop add newuser
```

Its beginnings
--------------
It was written to make it easy for someone who doesn't know linux to add, remove and edit user account details on a linux server with a simple default samba installation.
The script was designed for a Debian based distro of linux, but it should be easy enough adjust for other linux distributions by adjusting the configuration settings at the top of the script.


Operational detail
------------------

When the script is invoked with:

- add - Add the user to the linux system, then add the user to a 'default' group then add the user to the samba password database
- del - Delete the user account from the samba user database then remove the user from the system. The users home directory will not be deleted.
- pass - Modify both the system and samba passwords. As the script was put together in a bit of a rush it will ask the person running the script for the new password 4 times ( twice for the local system and twice again for the samba database )
- "gibberish"|help - The script will show you some help
- manual - The script will show you the manual commands you would need to perform the tasks manually  
