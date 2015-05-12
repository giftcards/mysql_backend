## Synopsis

This is a simple mysql backend for hiera intended to be used with puppet. It supports strings and arrays.

## Example

This backend is intended to be used primarily with parameterized classes, it has not been tested with hiera functions though they should work normally. Extended hiera option support is not installed, the lookups are intended to be simple with the backend doing the work to figure out of we have a string or list. Hashes are not supported.

*** arrays ***
This backend treats multiple results as arrays. For example, to return a list of 5 usernames you'll need to create 5 records with the same fields except for the value field.

## Motivation

This module was forked from crayfishx's hiera-mysql at https://github.com/crayfishx/hiera-mysql. It was intended to add array support and fix some bugs/odd behavior in the original version.

## Installation

All installation happens on the puppetmaster.
mysql_backend.rb should be placed in the ruby path under hiera/backends. Under CentOS 6 this is typically /usr/lib/ruby/site_ruby/hiera/backend/mysql_backend.rb.
The example hiera.yml should be placed at /etc/puppet/hiera.yml and modified to match your environment.
The sql statements are processed in order with the first hit being returned.
An example.sql is included which will create a schema that works with the includ
ed hiera.yml.

## Tests

On CentOS 6 you can test with the 'hiera' command by linking hiera.yml to /etc/hiera.yml.

## Contributors

Ryan Munz for Giftcards.com - May 2015
