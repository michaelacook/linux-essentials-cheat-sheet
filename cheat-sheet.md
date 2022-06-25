# Linux Essential Commands & Options

## Users and Groups

- View local users: 

    ```cat /etc/passwd```

- View users password info:

    ```sudo cat /etc/shadow```

- Create a user: 

    ```sudo useradd [username]```

- Create a user with a home directory: 

    ```sudo useradd -m [username]```

- Add home directory to user: 

    ```sudo mkhomedir_helper [username]```

- Add login shell to user: 

    ```sudo usermod -s [/path/to/shell]```

- Add a password to a user: 

    ```sudo passwd [user]```

- Lock/disable a user's password: 

    ```sudo usermod -L [user]```

- Unlock/enable a user's password: 

    ```sudo usermod -U [user]```

- Create a group: 

    ```sudo groupadd [group]```

- Add user to a group: 

    ```sudo usermod -a -G [groupname] [user]```

- Then optionally run `sudo source /etc/profile`

- Give a user sudo privileges: 

    ```sudo usermod -aG sudo [user]```

- Give a user sudo privileges on RHEL & derivatives: 

    ```sudo usermod -aG wheel [user]```

- Add all members of a group to the sudoer's group:

    ```sudo visudo```
- scroll to `%sudo` and add 

    ```bash 
    # Allow members of group sudo to execute any command
    %sudo   ALL=(ALL:ALL) ALL

    groupname ALL=(ALL:ALL) ALL
    ```

- Delete a user: 

    ```sudo userdel [user]```

- Delete a group: 

    ```sudo groupdel [group]```

- Remove a user from a group:

    ```sudo gpasswd -d [user] [group]``` 

-----

## Networking

- View IP addresses:

    ```ip addr show```
- Test connectivity:

    ```ping [domain|IP]```
- View DNS configurations:

    ```cat /etc/resolv.conf```
- Query A record for a host (get IP address for a domain): 

    ```dig [domain]```
- Query A record with a known DNS server:

    ```dig @[DNS server IP] [domain]```
- Map/view host names to IPs: 

    ```sudo vim /etc/hosts```

    ```cat /etc/hosts```
- View routing table: 

    ```ip route show```
- View network devices: 

    ```ifconfig```
- View network devices with more info, cleaner presentation: 

    ```nmcli```
- Print network connections: 

    ```netstat```
- Print TCP and UDP connections: 

    ``` netstat | grep -E "^t?c?u?d?p"```
- Dump socket statistics 

    ```ss```
- View ports and programs listening on them: 

    ```cat /etc/services```

-----

## Logs

- View system logs and messages: 

    ```less /var/log/messages```

- View system logs and message in Debian-based distros:

    ```less /var/log/syslog```
- View authentication logs:
    
    ```less /var/log/auth.log```
- View authentication logs in RHEL-based distributions:
    
    ```less /var/log/secure```
- View system boot logs: 

    ```less /var/log/boot.log```
- View cron job logs: 

    ```less /var/log/chron.log```
- View kernel logs: 

    ```less /var/log/kern.log``` 
- View messages from the kernel ring buffer: 

    ```dmesg```
- View authentication failure logs: 

    ```less /var/log/fraillog```

-----

## Processes

- View a snapshot of current running processes: 

    ```ps```
- View a dynamic real-time view of running processes: 

    ```top```
- Dump all running processes in BSD syntax:

    ```ps aux```
- Dump all running processes in Linux syntax:

    ```ps -eF```
- View all running processes for a user in BSD syntax: 

    ```ps aux | grep -E "^user"```
- View number of running processes: 

    ```ps aux | wc -l```
- View files associated with a process: 

    ```ll /proc/[PID]```

-----
