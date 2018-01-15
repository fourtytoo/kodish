# kodish
Shell scripts to control Kodi remotely

A bunch of shell scripts that do all I need to do on my Kodi server.
As for now, it doesn't try to be a complete mapping of the Kodi REST
API into shell commands.  And probably never will.

The cornerstone is `kodi-rpc`, which does the actual communication.

Have a look at kodi-breakfast-time or kodi-night-time to see how
these scripts work and interact with one another.

To use these scripts you need to have curl(1) and jq(1) installed on
your system.  You also need to provide your own `~/.kodish.cfg` with
some meaningful configuration.  Like this:

```sh
USER=username
PASSWORD=password
HOST=localhost:8080
```

## Caveats
Anyone who used a Kodi remote, whether an Android app or its web
interface, knows how reliable that is.  Not.

To just give you an example, on certain errors (especially if you play
internet radio, you will get them) Kodi pops up a dialog window on the
TV screen and waits for the user to acknowledge the problem. Thus
possibly requiring the user to walk back to the living room, where the
player is sitting, find the IR remote, turn the TV on, figure out why
the music stopped playing, and press OK.  All the while the REST
interface becomes unresponsive, waiting for the pop dialog to
disappear.

Kodi behaviour reflects its primary use as video player and doesn't
work well headless or remotely.  These shell scripts add to its
unreliability.

That is to say, do _not_ rely on Kodi to wake up in the morning.
