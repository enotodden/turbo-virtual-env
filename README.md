turbo-virtual-env
=================

A simple script to install Turbo, LuaJIT and LuaRocks in a self-contained directory.
Inspired by the `virtual-env` python tool.



What it does:
-------------

+ Clones LuaJIT, Turbo and LuaRocks, builds them and installs them to a self-contained directory.
+ Creates a source-able activation script that modifies PATH, etc.



Get started:
------------

#### Really quickly:

    $ cd /path/to/my/project
    $ curl https://raw.github.com/enotodden/turbo-virtual-env/master/turbo-virtual-env | bash -s - --create ./env
    $ source ./env/bin/activate



#### Quite quickly:

    $ git clone https://github.com/enotodden/turbo-virtual-env.git 
    $ cd turbo-virtual-env
    $ cp turbo-virtual-env /some/where/in/$PATH
    $ cd /path/to/my/project
    $ turbo-virtual-env --create ./env
    $ source ./env/bin/activate


Extra features:
---------------

#### Turbo Development Mode

`turbo-virtual-env` also takes an optional --turbo-dev argument to 
use the tool with an existing Turbo source directory.

    $ turbo-virtual-env --create ./path/to/my/env --turbo-dev /path/to/my/turbosrc


#### LuaRocks Requirements File

By passing the `-r` or `--luarocks-requirements` to `turbo-virtual-env`
it will read the supplied file line by line and run the contents of that line
as arguments to `luarocks install`



Examples:
---------

#### Creating a new Turbo project with dependency from LuaRocks:

This example shows how to create a new environment with the 'penlight' 
package from luarocks as a dependency.
     
    $ cd /tmp
    $ mkdir myproject
    $ cd myproject
     
    $ #Tell turbo-virtual-env to pass 'penlight' to luarocks for installation
    $ echo "penlight" >> ./requirements.txt
     
    $ turbo-virtual-env --create ./env -r ./requirements.txt
     
    $ # Activate virtual environment
    $ source env/bin/activate # Activate our virtual environment
     
    $ lua #lua is symlinked to luajit binary
    LuaJIT 2.0.2 -- Copyright (C) 2005-2013 Mike Pall. http://luajit.org/
    JIT: ON CMOV SSE2 SSE3 SSE4.1 fold cse dce fwd dse narrow loop abc sink fuse
    > require("pl")
    > if path.isdir("/") then print("Suprise! '/' is a directory!") end
    Suprise! '/' is a directory!
    > 



Dependencies:
------------

Only stuff that most people have installed already.

+ bash
+ git
+ curl
+ Basic build tools like gcc, make etc. (apt-get install build-essential on debian based distros)



