turbo-virtual-env
=================

A simple script to install Turbo and LuaJIT in a self-contained directory.
Inspired by the `virtual-env` python tool.



What it does:
-------------

+ Clones LuaJIT and builds it
+ Clones turbo and builds it
+ Creates a source-able activation script that modifies PATH, etc.



Get started really quickly
--------------------------

    $ cd /path/to/my/project
    $ curl https://raw.github.com/enotodden/turbo-virtual-env/master/turbo-virtual-env | bash -s - --create ./env
    $ source ./env/bin/activate



Get started quite quickly
-------------------------

    $ git clone https://github.com/enotodden/turbo-virtual-env.git 
    $ cd turbo-virtual-env
    $ cp turbo-virtual-env /some/where/in/$PATH
    $ cd /path/to/my/project
    $ turbo-virtual-env --create ./env
    $ source ./env/bin/activate


Turbo Development Mode
----------------------

`turbo-virtual-env` also takes an optional --turbo-dev argument to 
use the tool with an existing Turbo source directory.

    $ turbo-virtual-env --create ./path/to/my/env --turbo-dev /path/to/my/turbosrc
