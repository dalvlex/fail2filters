# fail2filters
fail2ban filters (apache2, nginx, ssh etc.) and configuration

### Dependencies: fail2ban, sqlite3
`apt install sqlite3 fail2ban`

### Rules
- new filters in filter.d/ and new jails in jail.d/ will be prefixed with 'f2f-'
- jails and filters will have the same name

### Commands
`./install` - installs and uninstalls the configuration from the fail2filters repo  
`./install update` - updates the local files from the current fail2filters repo
