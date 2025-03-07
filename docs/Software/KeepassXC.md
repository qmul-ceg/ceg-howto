
## KeepassXC Databases
- **CEG_Keys** Contains passwords and keys for admin access.
	- `CEG Operational>>Data Governance>>KeePassXC>>CEG_Keys.kdbx`
	- Secured by key file - `CEG Operational>>Data Governance>>Server Keys>>KeePass>>CEG_Keys.keyx`
- **Kelvin_Keys** Contains Kelvin's passwords and keys.
	- `QM OneDrive>>KeepassXC>>Kelvin_Keys.kdbx`
	- Secured by
		- Key file: `QM OneDrive>>.ssh>>kelvin_keys.keyx`
		- Password: in Home database
## Add Key File
Any file can be used as a key file as long as
	a) the file never changes
	b) it contains unpredictable data.
But best to let KeepassXC generate file for you.
- Database -> Database Settings -> Security
- Add Key File ~> Generate
	- Select the location where to save the key file, make sure the path to the new file is inserted into the Key File field, and 
- Save database.
- Backup key file in a safe place!
## AutoOpen
Enable databases to automatically open when another database is opened.
Open 'Home' database automatically opens and logs into 'Kelvin_Keys' database, which in turn opens and logs into 'CEG_Keys'.
- Create AutoOpen folder and a New Entry
	- Title = *name of database to be opened* eg `KeePassXC [CEG_Keys]`
	- Username = *path to database key file (.keyx)*
		- note - relative paths (`{USERNAME}`etc) don't work.
	- Password = *password or leave blank if just using key file*
	- URL = *path to database file (.kdbx)*
