# fail2filters
fail2ban filters (apache2, nginx, ssh etc.) and configuration

### Dependencies: fail2ban, sqlite3
`apt install sqlite3 fail2ban`

### Rules
- new filters in filter.d/ and new jails in jail.d/ will be prefixed with 'f2f-'
- jails and filters will have the same name

### Commands
`./install update` - updates the local files from the current fail2filters repo;  
`./install 1` - installs the fail2filters configuration files into your fail2ban configuration folder (probably /etc/fail2ban);  
`./install 2` - uninstalls the fail2filters configuration files from your fail2ban configuration folder (probably /etc/fail2ban);  

**WARNING:**
- upon 'install' or 'uninstall', fail2filters will empty the fail2ban.d & jail.d folders in your fail2ban configuration folder!  
- when using 'update' all your local filters and jails in the fail2filters folder will be deleted.

