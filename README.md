# kodish
Shell scripts to control Kodi remotely

A bunch of shell scripts that do pretty much anything I need to do
remotely on my Kodi server. As for now, it doesn't try to be a
complete mapping of the Kodi REST API into shell commands.  And
probably never will.

The cornerstone is `kodi-rpc`, which does pretty much all the heavy
lifting.

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
interface, knows how clunky and unreliable that is.  To just give you
an example, on certain errors Kodi would pop up a dialog window and
wait for the user to acknowledge the problem.  That is, even if the
error was due to a REST command.  The REST interface, in such cases,
gets stuck as well.  The Kodi REST API is not pretty and these shell
scripts add to its unreliability.

That is to say, do _not_ rely on Kodi to wake up in the morning.
