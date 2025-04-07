
### Install PuTTY
https://www.putty.org/
  
#### Add SSH Key  
Host Name (or IP address): 192.168.1.136  
Port: 22  
Connection Type: SSH  
In lefhand Category Panel  
Navigate to Connection >> SSH >> Auth  
Browse to Serverkey1.ppk location  
In lefthand Category Panel  
Navigate back to Session  
Saved Sessions: CEG-VPN  
Save  
\- CEG-VN should now be in the list of Saved Sessions

#### Generate SSH Key
Open PuTTY Key Generator
Load pem file (look for All Files) OK notice
Save private key (use same name as pem) - no password
creates ppk file
copy  pem and pkk to secure store
copy pkk to connection device

From May 2021 PuTTY has introduced a new version of ppk.
For compatibility with pre v.075 PuTTY and other SSH clients, change PuTTYgen settings:
Go to Key>>Parameters for saving key files...
And change the PPK file version to  2.
