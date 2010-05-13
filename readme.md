# Nginx Vhost Tools

Some tools I've written to help me save time in creating/using nginx vhosts.

## Tools

The following tools are developed for an apt install of nginx-brightbox (nginx & passenger) on Ubuntu 10.04. They expect your sites to be defined in `/etc/nginx/sites-available`, but only read as part of the nginx config after being symlinked into `/etc/nginx/sites-enabled`.

### `ngen` and `ngdis`

Enables or Disables virtual hosts.

	$ ./bin/ngdis caius.name
	/etc/nginx/sites-enabled/caius.name
	Disabled 'caius.name'

	$ ./bin/ngen caius.name 
	/etc/nginx/sites-enabled/caius.name
	Enabled 'caius.name'


### `ngnew`

Generates and saves a new nginx config for a domain name.

	$ ./bin/ngnew --help
	USAGE: ngnew [options]

	Specific options:
	    -n, --name NAME                  Domain name
	    -u, --user [USER]                Username where webroot resides
	    -t, --template [FILE]            File to read template config from
	    -f, --file [FILE]                File to write config into
	        --enable-php                 Enable PHP in the vhost

use `%USER%`, `%NAME%` and `%PHP_CONFIG%` as variables in your template file. `%PHP_CONFIG%` is hardcoded to just `include php_config;`, so put your generic php config in `/etc/nginx/php_config` for it to be included.

Defaults to reading template file from `/etx/nginx/template`, writing config file to `/etc/nginx/sites-available/$NAME` and the shell user running the script.

## License

Copyright (c) 2010 Caius Durling <dev@caius.name>

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.
