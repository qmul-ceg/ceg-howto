## Service Status
Check status of service `sudo systemctl status openvpn-server@server.service`. 
This provides a reason if the service has failed to run. `Ctl C` to exit.
To try to reboot `sudo systemctl restart openvpn-server@server.service`

### start / stop service
```bash
sudo systemctl status roonserver
sudo systemctl start roonserver
sudo systemctl restart roonserver
sudo systemctl stop roonserver
q
```

### check running services
```bash
sudo service --status-all
```
\[ + ] means service is running.  Check for fail2ban, unattended-upgrades and ufw. And for anything suspicious.
```bash
sudo systemctl list-units
```
Failed services show in red.  
(This shows problems with VPN02 cloud-init, e2scrub_reap and snapd.seeded - but these do not affect the running of the server)

## check running processes
```bash
sudo ps aux  
```

### run and kill processes
```bash
sudo ps <-ef> | grep java
```` 
\-e all processes
\-f full-format listing
```bash
sudo kill -9 <process id>
```  

## check glances (if installed)
```bash
glances
^c
```


- `&&` means execute the statement which follows _only if_ the preceding statement executed successfully (returned exit code zero).
    
- `||` means execute the statement which follows _only if_ the preceding statement failed (returned a non-zero exit code).
    

Some of the other control operators are:

- `&` means execute the preceding statement in the background.
    
- `;` means execute the preceding statement and, after it completes, proceed to the next statement.
    
- `|` means execute the preceding statement and connect its stdout the to stdin of the statement which follows.
