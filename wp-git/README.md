# WP-GIT

## Purpose

These scripts are intended to make version control more useful for WordPress sites.  Whenever a commit is made, a snapshot of the database is taken in `db/` in the site root.  Whenever a pull is made, or code is reverted to a previous commit, the database snapshot will be imported into the database.

All credentials, database names, etc. are pulled automatically from `wp-config.php` in the site root.

## Installation

Copy script files to `.git/hooks/`.

## Notes

Make sure your file permissions are properly set to prevent tables from being publicly accessible.
