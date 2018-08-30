# fail2filters
fail2ban filters (apache2, nginx, ssh etc.) and configuration

### Install fail2filters
`git clone https://github.com/dalvlex/fail2filters /root/fail2filters`  
fail2filters is meant to be used as root and installed under /root/fail2filters, probably it would work as another user with sudo, but this is not tested!  
Create dummy logs for the jails you don't need, or disable them. If you want the git jails refreshed daily insert the cron entry from below - **this will overwrite your jails and filters**.

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

### Crontab
```
# Renew Ishi code from GitHub daily  
@daily /usr/bin/git -C /root/fail2filters reset --hard && git -C /root/fail2filters clean -f && git -C /root/fail2filters pull && /root/fail2filters/install 1 > /dev/null 2>&1
```
