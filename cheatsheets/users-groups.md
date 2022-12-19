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

Create a service account

```
sudo useradd -r -s /sbin/nologin -d [/path/to/service] [username]

# give service user ownership of home dir
sudo chown [username:username] /path/to/service
```

Create a user with a home directory 

```
sudo useradd -m [username]
```

Add home directory to user 

```
sudo mkhomedir_helper [username]
```

Add a user and specify primary group membership other than default

```
sudo useradd -g [primary group] [username]
```

Add a user and specify supplementary group membership

```
sudo useradd -G [group1, group2, ..., groupN] [username]
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

Set expiry date for an account

```
sudo chage -E [year-month-day] [username]
```

Remove expiry date for an account 

```
sudo chage -E -1 [username]
```

Change password expiry warning

```
sudo chage -W [number of days] [username]
```

View account settings

```
sudo chage -l [username]
```

Lock/disable a user's password 

```
sudo usermod -L [user]
```

Unlock/enable a user's password 

```
sudo usermod -U [user]
```

Create a group 

```
sudo groupadd [group]
```

Add user to a group: 

```
sudo usermod -a -G [groupname] [user]
```

Then optionally run `sudo source /etc/profile`

Change group ID number

```
sudo groupmod -g [number] [groupname]
```

Change group name

```
sudo groupmod -n [new name] [old name]
```

Give a user sudo privileges

```
sudo usermod -aG [sudo|wheel] [user]
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

------------------------------

### Location of configuration files

- `/etc/passwd` - user database
  - System accounts always have a user ID below 1000, root is 0
  - Standard user accounts usually have a user ID above <=1000
- `/etc/shadow` - encrypted password database
  - `$1$ = MD5`
  - `$2a$, $2y$ = Blowfish`
  - `$5$ = SHA-256`
  - `$6$ = SHA-512`
- `/etc/group` - group database, associates users with groups
- `/etc/skel` - contains items that are automatically added to a new user's home dir when the account is created
- `/etc/default/useradd` - this config file is referenced by the `useradd` command when a new user account is created
  - contains basic config defaults for new user accounts
    - Default group membership
      - default is 100, the old standard default users group
      - values in `/etc/login.defs` takes precedence over `/etc/default/useradd`
        - defaults for user group membership overridden in `/etc/login.defs`
    - location of home directory
    - inactive status - whether account becomes inactive if password expires - default -1, can change to 0 to make accounts inactive when password expires
    - expire - date account will expire - default no date given
    - default shell
    - default files for home dir, default is `/etc/skel`
    - create a mail spool for user, default is yes