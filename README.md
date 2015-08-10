tweet.pl
========

A simple utility to send a tweet via a command-line tool.

Syntax:

```tweet.pl [--to=<Direct Message recipient>] [--host=<host>] [--type=<direct|update>] [--eventtype=<event>] [message]```

The defaults are to send an `update` to your own account.  If `--type=direct`
is specified then the account specified by `--to` is used.  If an `--eventtype`
is specified then this will be pre-pended to `message` along with the value of
`--host`, or 'unknown' if not specified.

Manual configuration
====================

A Twitter `consumer secret` and `comsumer secret key` are required to interact
with the Twitter API - these can be obtained by creating a new App at
https://dev.twitter.com from a Signed-In twitter account.  The permissions of
this custom App should then be updated to take it out of Read-Only mode.

A configuration file is looked for in `/etc/tweet.pl.conf`, `~/.tweet.pl.conf`,
or `tweet.pl.conf` in the same directory as `tweet.pl` itself.  If none of
these can be read, then a default `~/.tweet.pl.conf` will be created.

This file will resemble the following:

```
[default]
dm_account = <blank or a specified account>

[keys]
consumer_key_secret = <secret from dev.twitter.com>
consumer_key = <key from dev.twitter.com>

[tokens]
access_token = <blank>
access_token_secret = <blank>
```

When you first run the script you'll be prompted to visit a Twitter URL and
then input the provided PIN, which will populate and save an Access Token and
Access Token Secret pair to your configuration file.

If the environment variable `DEBUG` is set then more verbose messages will be
output, and if `notweet` is set then `tweet.pl` will perform all processing
(including connecting to the Twitter API), except for actually sending the
specified tweet.

The perl module `Config::Simple` is now a pre-requisite to run `tweet.pl` -
please checkout commit [976fe3c](https://github.com/srcshelton/tweet.pl/tree/976fe3c1e864ecd359552bfad74ca90c91d20633)
for the older release, which requires that values be hard-coded but which
doesn't use any non-core modules.

Patches welcomed ;)

