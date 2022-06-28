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