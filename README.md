My Bash Profile
===============

This is the profile that I use daily. A big thanks to [Mat Schaffer](https://github.com/matschaffer) to make his profile public.

What's it look like?
--------------------

![Feature Diagram](http://farm4.staticflickr.com/3730/11277216155_9518a903fb_z.jpg)

Installation
------------

    curl -s https://raw.github.com/popox/profile/master/install | bash

From here you can now put any `*.conf` in `~/.profile.d` and it'll get loaded in alphabetical order. You can also make directories that end in `.conf` which profile will then load all the `.conf` files in that directory in order.

Additionally, if you need to have OS-specific configuration just put a folder in `.profile.d` or `.profile.d/core` with the name returned by `uname`, for example `.profile.d/Darwin`. The profile checks `uname` when bash starts and loads any `.conf` files or directories in this OS-specific folder.

__Note:__ Set your fav editor in `~/.profile.d/editors.conf`

Load order
----------

This profile loads `init` first, followed by all the `.conf` files in `.profile.d/core`, then any `.conf` files in `.profile.d`. This way you can put any general use configs in `core` and anything personal in `.profile.d`. If you want to keep your personal profile information in git, just set up `core` as a submodule to your personal repository.

Features
--------

This list is not guaranteed to be comprehensive, but here are some of the major features included as of the last time this document was updated.

* Reactive prompt - includes date and exit code of last command and git branch.
* Tab Completion for Git and Subversion
* Tab completion for Rake, Maven 2 and Ant
* Tab completion for ssh hosts on OS X.
* Git aliases
* 'safeedit' function that makes a timestamped backup copy of a file before editing
* Basic java set up on solaris and Darwin
* Maven memory settings
* 'profile_push' function for pushing these files out to other servers
* Auto setup of .foward file on Linux and Solaris
* Integration with [CDArgs](http://www.skamphausen.de/cgi-bin/ska/CDargs)
* Integration with [Autojump](http://github.com/joelthelion/autojump/)
* Integration with [RVM](http://rvm.beginrescueend.com/)

Contributing
------------

As noted in the LICENSE file. This is all MIT licensed code, so do what you will. But to make things easy for contributions please keep all stuff in core as generic as possible so others can merge it into their own forks. If you need any personal stuff (e.g., API Keys), keep that in a separate git repository that loads this repo as a submodule.
