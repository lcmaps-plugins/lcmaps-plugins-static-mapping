
# lcmaps-plugins-static-mapping

![][https://api.travis-ci.org/lcmaps-plugins/lcmaps-plugins-static-mapping.svg?branch=master]

This LCMAPS plugin does a mapping solely based on the contents of a mapfile.
The contents of the mapfile, assumed to be /etc/grid-security/glexec-mapfile.
This can be overridden with the -mapfile argument, if desired.

The contents of the mapfile should be something like this:

```
# This is a comment
jobslot001 postglexec_jobslot001
jobslot002 postglexec_jobslot002
jobslot003 postglexec_jobslot003
jobslot004 postglexec_jobslot004
```

The first column is the invoking user; the second column is the target user.
Only usernames, not UIDs, are supported.

Once matched, the plugin will lookup the UID, primary GID, and secondary GIDs
of the target user.

