## Users and Groups

View local users: 

```
cat /etc/passwd
```

View users password info

```
sudo cat /etc/shadow
```

Create a user

```
sudo useradd [username]
```

Create a user with a home directory 

```
sudo useradd -m [username]
```

Add home directory to user 

```
sudo mkhomedir_helper [username]
```

Add login shell to user 

```
sudo usermod -s [/path/to/shell]
```

Add full name to a user account

```
usermod -c "Full Name" [user]
```

Add a password to a user

```
sudo passwd [user]
```

Require password reset on first login

```
passwd -e [user]
```

Lock/disable a user's password 

```
sudo usermod -L [user]
```

Unlock/enable a user's password 

```
sudo usermod -U [user]
```

Create a group: 

```
sudo groupadd [group]
```

Add user to a group: 

```
sudo usermod -a -G [groupname] [user]
```

Then optionally run `sudo source /etc/profile`

Give a user sudo privileges: 

```
sudo usermod -aG sudo [user]
```

Give a user sudo privileges on RHEL & derivatives: 

```
sudo usermod -aG wheel [user]
```

Add all members of a group to the sudoer's group:

```
sudo visudo
```
- scroll to `%sudo` and add 

    ```bash 
    # Allow members of group sudo to execute any command
    %sudo   ALL=(ALL:ALL) ALL

    groupname ALL=(ALL:ALL) ALL
    ```

Delete a user 

```
sudo userdel [user]
```

Delete a user and their home directory simultaneously

```
sudo userdel -r [username]
```

Delete a group 

```
sudo groupdel [group]
```

Remove a user from a group

```
sudo gpasswd -d [user] [group]
``` 

Login as a user 

```
su [user]
```

Login as the root user 

```
sudo su -
```

Login as the root user

```
sudo -i
```

Logout as a user

```
exit
```