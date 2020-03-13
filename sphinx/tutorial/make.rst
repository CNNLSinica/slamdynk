.. _make:

====================
Introduction to make
====================

`Make <https://www.gnu.org/software/make/>`_ is a build tool that can be used in software development to search dependecies and 
compile source code into executable programs or libraries.

----

Using make
----------

* make options

  * --environment-overrides (-e)
  * --ignore-errors (-i)
  * --print-data-base --question
  * --just-print
  * --debug=option1, option2, ...
  * --keep-going (-k)\: ignore error
  * --directory=directory (-c)\: change directory
  * --file (-f) <specified file>
  * -n\: dry-run

----

Rule of makefile
----------------

::

 target: dependency(prerequisite) ...
     action

:target: the file to be created or built
:dependency: the necessary files to build the *target*
:action: run command when *dependency* is satisfied

Special Target
--------------
* .PHONY


Automatic variables
-------------------

:$@: target
:$^: all dependencies
:$<: first dependency
:$%: archive member (ex: foo.a(bar.o) --> $% = bar.o)
:$?: all dependencies which timestamp after target
:$+: similar to $^, but include replicates
:$*: [stem].suffix
:$$: subshell variables
:$(@|^|<\|\.\.\.D): only directories
:$(@|^|<\|\.\.\.F): only files
