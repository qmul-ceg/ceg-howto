# Format Private Key for use in PuTTY (from .  or .pem file)
## using PuTTYgen
Load the private key (look for All Files). OK the notice.
Add passphrase - can leave blank
Save private key - with file name and .ppk extension.

From May 2021 PuTTY has introduced a new version of ppk.
For compatibility with pre v.075 PuTTY and other SSH clients, change PuTTYgen settings:
Go to Key>>Parameters for saving key files...
And change the PPK file version to  2.