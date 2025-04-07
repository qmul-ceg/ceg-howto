# Copy Public Key to Resource (server, github etc)
## on Windows (using manual copy)
- Open the .pub in a text editor and copy as needed.  . You can do this from the terminal:
```bash
notepad C:\Users\Username/.ssh/ssh_key.pub
```

## on Linux
- cd to home, create the .shh folder, if it doesn't exist and copy the public-key-$tring into the authorized_keys file. Ensure file has access restricted to owner
```bash
cd ~
mkdir -p ~/.ssh
echo public-key-$tring >> ~/.ssh/authorized_keys
chmod 600 authorized_keys
```

## on Windows (using PowerShell)
- Requires server's {IP-or-FQDN).
```terminal
type $env:USERPROFILE\.ssh\home-ubuntu.pub | ssh {IP-or-FQDN} "cat >> .ssh/authorized_keys"
```
Confirm to continue connecting and provide password for user login
https://www.chrisjhart.com/Windows-10-ssh-copy-id/

