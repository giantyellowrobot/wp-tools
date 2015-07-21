# WP-TOOLS

A set of generally useful tools to make WordPress easier to live with

## What's In The Box

### wp-git

A set of git hooks to make version control useful for WordPress.  Does two things:

1. When committing changes to git, exports the database to `db/{database name}.sql` and includes this file in the commit
1. When pulling from a remote branch, imports the `db/{database name}.sql` file into the database

This allows changes to site content, settings, etc. to be tracked in version control.

Usage:

1. Initialize a git repo in your wordpress directory if you haven't already
1. Copy all scripts in `wp-tools/` to `{wordpress install dir}/.git/hooks`

The scripts operate silently and pull all necessary credentials and database info from `wp-config.php`.

### wp-install

Shell script to install WordPress from the terminal.  Can be run with `./wp-install` and will prompt for all necessary information.  Automatically creates the database and database user and populates `wp-config.php` with the relevant database info.  Does not set file permissions properly - use the `setpermissions` script after install.

### setpermissions

Shell script to properly set permissions for a WordPress install.  Usage: `sudo ./setpermissions {install dir}`

### db-snapshot

Shell script to quickly export a DB snapshot from a WP install.  Reads database credentials from `wp-config.php`.  Usage: Copy to WP root dir and run `./db-snapshot`