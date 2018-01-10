# kodish
Shell scripts to control Kodi remotely

A bung of shell scripts that do pretty much anything I need to do
remotely on my Kodi server. As for now, it doesn't try to be a
complete mapping of the Kodi REST API into shell commands.  And
probably never will.

The cornerstone if `kodi-rpc` which does pretty much all the heavy
lifting.

Have a look into kodi-breakfast-time or kodi-night-time to see how
these scripts work and interact with one another.

To use these scripts you need to have curl(1) and jq(1) installed on
your system.
