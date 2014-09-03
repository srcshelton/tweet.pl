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

`save_tokens` and `restore_tokens` are currently stubs, either in need of
implementation or for the requisite tokens values hard-coded. Currently, when
you first run the script you'll be prompted to visit a Twitter URL and then
input the provided PIN, which will output an Access Token and Access Token
Secret pair, which should then the hard-coded into the current implmentation of
the `save_tokens` function.

The (optional )default DM `$account` as well as your account's `$comsumer_key`
and `$consumer_key_secret` do currently need to be hard-coded at the top of the
file, although in the future these values should (also) be read from an
external configuration file.

This script doesn't currently use Getopt::Long (which it should), and so
arguments must be specified exactly as per the usage string above.  If a space
is substituted for a '=' character, then the result will not be what you might
expect!

Patches welcomed ;)

