.. _install:

============
Installation
============

Requirements
============

- ase-3.19.0
- amp-atomistics-0.6.1
- tensorflow-2.0.0
- tensorflow-probability-0.8.0
- keras-2.3.1
- mpi4py
- lammps-22Aug18
- vasp.5.4.x

Installation from Source
========================

1. Get the latest release from https://github.com/CNNLSinica/slamdynk

::

    $ git clone https://github.com/CNNLSinica/slamdynk.git

2. make

::

    $ make
    $ cd build

or

::

    $ make build_c
    $ cd build_c

3. Initialize the program

::

    $ bash init.sh

p.s. for the latest version of training module :ref:`ann_tflow`, please refer to `here <https://ardahsieh.github.io/ANN-tflow-guide/>`_.

Getting Started
===============

Prepare the initial structure ...
