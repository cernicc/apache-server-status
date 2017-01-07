# Apache Server Status Example (mod_status)

Docker image builded from this repository is used for showing status of Apache server. When container is started visit http://localhost/server-status 

For using in production change 

```
<Location /server-status>
    SetHandler server-status
    Order allow,deny
    Allow from all
</Location>
```

to something like

```
<Location /server-status> 
    SetHandler server-status 
    Order allow,deny
    Deny from all
    Allow from 192.168.1.100
</Location>
```

Where 192.168.1.100 is your internal IP if accessing internally or your external IP. This will restrict it so not just anyone can access server status.
