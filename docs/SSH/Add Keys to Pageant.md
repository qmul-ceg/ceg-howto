# Add keys to Pageant
- **Pageant** ~> Add Key
	- Browse to ppk file
	- Provide passphrase
- View keys to see loaded keys

## Set Pageant to load at Windows Startup
- copy *C:\Program Files\PuTTY\pageant.exe* and paste as shortcut in *C:\Users\Kelvin\AppData\Roaming\Microsoft\Windows\Start Menu\Programs\Startup\*
https://talesfromthedatacenter.com/2019/12/how-to-automatically-load-pagent-keys-when-windows-10-boots/

## Add keys to KeepassXC
### initial setup
- **KeepassXC / Settings / SSH Agent** ~>
	- Tick *Enable SSH Agent integration*
	- Tick *Use Pageant* or *Use OpenSSH*
- OK
### add key
- **KeepassXC** ~> New Entry
	- Title = Entry Name
	- Password = key passphrase
	- ~> **Advanced**
		- Attachments / Add ~> select OpenSSH private key
	- ~> **SSH Agent**
		- Private key / Attachment ~> select attached key
		- Tick Add key to agent...
		- Tick Remove key from agent...
	- OK
### add key to agent
- key will automatically load into agent when KeepassXC is opened
- alternatively - highlight entry
	- Right-Click ~> Add key to SSH Agent
	- Ctl H


##### In Git Bash:
Check ssh-agent is running
```bash
eval "$(ssh-agent -s)"
```
Should return the Agent pid number.

Add ssh private key to ssh-agent. (Change ssh_key to the name of the key).
```bash
ssh-add ~/.ssh/ssh_key
```
## auto-start ssh-agent
The ssh-agent needs to started for each session and loaded with the key. ssh-agent can be set to auto-load by creating c:\Users\{username}\.bashrc with commands
```bash
notepad ~/.bashrc
```

```bash
eval `ssh-agent`
ssh-add
```

Open a new Git Bash terminal. Git will recognise the .bashrc file, complain that there is no .bash_profile file and auto-generate it.
The ssh-agent will now be reported at the start of any new Git Bash terminal.  Load the ssh key to connect to Github.
```bash
ssh-add ~/.ssh/ssh_key
```

# BUT
There can be issues with using key direct in ssh-agent.  This blog post goes into details with a link to more complex .bashrc setup.
https://rabexc.org/posts/pitfalls-of-ssh-agents