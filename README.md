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

`save_tokens` and `restore_tokens` are currently stubs, either in need of
implmentation or for the requisite tokens values hard-coded.

The default DM `$account` and your account's `$comsumer_key` and
`$consumer_key_secret` do currently need to be hard-coded at the top of the
file, although in the future these values should (also) be read from an
external configuration file.

Patches welcomed!
