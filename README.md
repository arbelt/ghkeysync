---
title: ghkeysync
---

## ghkeysync

Silly but half-useful project for messing around in Perl.

This sophisticated script to fetches SSH keys from Github and merges them into an
`authorized_keys` file. If desired, it is also possible to output to STDOUT, but
this functionality may need further testing.

Cutting-edge features:

- Fetching keys from one, two, three, four, five, six, and even more users with
  a single invocation. Users are specified by `--user` option arguments, e.g.,
  `ghkeysync --user arbelt --user otherid`.
- Keeps track of which keys it manages and which it doesn't with future-proof
  text-tag technology. It sets the comment fields of managed keys to
  `$tag:$user`. The `$tag` portion is even... wait for it... **customizable**
  using the `-c` flag.
- Automatically detects duplicate key entries and will not insert keys that
  already exist
- Removes "old" keys that are marked as belonging to a user but no longer appear
  in Github
- "Purge" option to keep only keys belonging to specified users (as well as
  unmanaged keys)

This script always re-inserts keys that it does not manage. Except duplicates,
which are inserted once, with the comment field coming from the first copy. At
least in theory, at some point the code got messy and I can't be sure of what it
actually does anymore, but it seems to work.
