# Deprecated

Some of the info here is useful, but also horrifically out of date and made when I was still learning the tool chain. In particular, the CMake example is very amateurish and you should not use it as a basis for your projects.


Project Templates for C and C++
===============================

What
----

This is a set of some of the templates I start with whenever I begin a new project. I
am the kind of person who prefers using a simple setup of an editor, build scripts,
and OS utilities to do my development.

The way I usually develop is by having two terminals open at the same working directory:
one for using vim and other tools to make changes to source files, and the other to build
the project and run/debug the program (speaking of which, you should look into using cgdb).
I usually have another monitor to work with, which I use to view and switch between a web
browser, documentation, and IRC.

These templates are Linux-centric.  However, it should not take too much work to
adapt the CMake template(s) to work on the OS of your choosing.

If you are completely new to C++ and C, I recommend you get familiar with how to build
an executable manually first (it's easy), and then use tup.  It is by far the simplest
build system to use, and offers a quite a few useful features without having a steep
learning curve.


Build systems
-------------

- gmake
    - usually either installed by default or not difficult to get your hands in
      most Linux distros.
- tup
    - a non-standard build system.  is very lightweight, and has few dependencies,
      so should be easy to install
- cmake
    - heavyweight build system.  may require a lot of dependencies, depending on
      what you already have on your system.


gcc vs. clang
-------------

Most (or likely all) of my examples make use of the GNU compiler collection, as
that is the compiler I prefer using.  However, you should be able to swap in clang
or the compiler of your choosing without much headache (a couple of compiler
parameters I use may not be supported by clang, though).


Some Remarks
------------

### Makefiles

Makefiles are the traditional way to build C and C++ projects on Unix.  They are
reliable, dependable, have reams of documentation online.  However, it isn't
exactly portable, even better different Unix-likes and in extreme cases, between
different Linux distributions.  An advantage of Makefiles is that they allow
you to easily specify rules and procedures related to building, so you can write
things like `make install`.  Also not portable, but handy.


### Tup

Tup is an incredible build system which I use almost exclusively for all of my
recent projects.  I have no idea how well it supports development on systems that
are not Unix-likes, as I have been using it exclusively on Linux.  It is very easy
to learn, assuming you are already familiar with how to build C or C++ projects by
hand.

Tup's website describes its features and advantages far better than I ever could.  I
encourage you to visit them.


### CMake

CMake is an improvement over using plain Makefiles, and one of its biggest selling
points is that it allows you to write cross-platform build scripts easily.  I
find it a bit too clunky for the small- to medium-sized projects I usually write.
I also tend to dislike opaque abstractions, and CMake is big on opaque abstractions.
Your knowledge of existing build systems and platform tools is almost useless when
using CMake; it has its own process and set of arcane functions for you to learn.


### Windows

I am not familiar with how C and C++ development is done on Windows, but from what
I've seen, it revolves around using batch files or Visual Studio.


Misc. Notes
===========

On includes
-----------

Don't seperate them from your source files.  It may seem neater, but it really isn't,
and just gives you more headaches in the long run.  Treat source and header files as an
inseperable couple, with the source being the implementation and the header being the
interface.  If you do not want hundreds of files in a source directory, you should
do something like Java's packages, by grouping your functionality into modules and
organizing them into their own directories.


TODO
====

I've started off with a set of minimal build scripts - everything you need so that you
may just build and run your program.  However, build systems are capable of so much more.
I hope to explore more topics in future.

0.  Automated builds using inotify or polling
1.  Passing defines to the preprocessor
2.  Development and debugging builds vs. optimized release builds
3.  Linking, `pkg-config`, and friends
4.  Building dynamic libraries and modules
5.  Using Qt without qmake or QtCreator (I don't have high hopes for this one)
6.  More?

