Directory Lookup
================

#### A command line tool to store and retrieve long directory paths using short aliases ####

Installation
------------

Dependencies: ruby, sqlite3

1. Place the included ruby script *dl* somewhere on your path.
2. Insert this code into your .bash_aliases file:

    cd_to_alias() {
      path=`dl find $1`
      if [ "$?" -eq "0" ]; then
        cd $path
      else
        echo $path
      fi
    }
    alias go="cd_to_alias $1"

Usage
-----

To assign a shortcut alias to the current directory:

    $ dl add short

Where *short* is the name you wish to associate with this path.

If you created a cd command alias as shown above, you can then type:

    $ go short

This will change directory to the path associated with *short*.

To remove an alias, just use:

    $ dl remove short

