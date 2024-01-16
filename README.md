# About Watcher

Watcher is a daemon that watches specified files/folders for changes and
fires commands in response to those changes. It is similar to
[incron](http://incron.aiken.cz), however, configuration uses a simpler
to read ini file instead of a plain text file. Unlike incron it can also
recursively monitor directories.

It's written in Python, making it easier to hack.

## Requirements

This fork is updated for Python 3 to run on Ubuntu 22.04 and similar.
Watcher uses the [pyinotify](http://github.com/seb-m/pyinotify) library.

In Ubuntu (and Debian) you can install it with:

    sudo apt-get install python3-pyinotify

## Configuration

See the provided `watcher.ini` file for an example job configuration. The
config file should reside in `/etc/watcher.ini` or `~/.watcher.ini`. You
can also specify the path to the config file as a command line parameter
using the `--config` option.

If you edit the ini file you must restart the daemon for it to reload the
configuration.

## Starting the Daemon

Make sure watcher.py is marked as executable:

    chmod +x watcher.py

Start the daemon with:

    ./watcher.py start

Stop it with:

    ./watcher.py stop

Restart it with:

    ./watcher.py restart

Debug it with: (log output to console)

    ./watcher.py debug

If you don't want the daemon to fork to the background, start it with

    ./watcher.py debug

