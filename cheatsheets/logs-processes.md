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