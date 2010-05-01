# Nginx Vhost Tools

Some tools I've written to help me save time in creating/using nginx vhosts.

## Tools

### `ngen` and `ngdis`

Enabled or Disabled virtual hosts. Assumes you keep your virtualhost files in `/etc/nginx/sites-available` and symlink them into `/etc/nginx/sites-enabled` to activate them.

	$ ./bin/ngdis caius.name
	/etc/nginx/sites-enabled/caius.name
	Disabled 'caius.name'

	$ ./bin/ngen caius.name 
	/etc/nginx/sites-enabled/caius.name
	Enabled 'caius.name'

