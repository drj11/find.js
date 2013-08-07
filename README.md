# find.js

POSIX compliant find in node.js (not POSIX
compliant yet)

# Where

https://github.com/drj11/find.js

# Implementation Status

## Implemented

* `-a` and `-o` (with correct precedence)
* `-type f` and `-type d` and `-type l` and `-type p`
* `-exec`
* `-ok`
* `-links`
* `-newer`
* `-print`
* `-prune`
* `-size`
* `-depth`
* implicit `-print`
* implicit `-a`

## Technical Notes

When using `-newer file` and *file* is symbolic link, should we
use the mtime of the link or the file referenced by the link?
The current implementation uses `fs.stat` and therefore uses the
file referenced by the link. Follow-up question, should this be
changed by the `-H` or `-L` options?
