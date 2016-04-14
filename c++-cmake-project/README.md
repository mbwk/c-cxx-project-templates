CMAKE PROJECT TEMPLATE
======================

Initializing a CMake project:

    $ mkdir bin
    $ cd bin
    $ cmake -G "Unix Makefiles" . ../
    $ cd ..
    $ cmake --build bin


Make changes to source files, compile changes, run executable:

    $ $EDITOR src/main.c
    $ cmake --build bin
    $ bin/example

