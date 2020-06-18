.. _install:

============
Installation
============

Requirements
============

- ase==3.19.0
- amp-atomistics==0.6.1
- tensorflow==2.0.0
- tensorflow-probability==0.8.0
- keras==2.3.1
- mpi4py
- lammps-22Aug18
- vasp.5.4.x

Installation from Source
========================

1. Get the latest release from https://github.com/CNNLSinica/slamdynk

::

    $ git clone https://github.com/CNNLSinica/slamdynk.git

2. Make, and install the package

::

    $ make
    $ cd build
    $ python install.py [pydir]

or

::

    $ make build_c
    $ cd build_c
    $ python install.py [pydir]

3. Export the PATH

::

    $ export PATH=$PATH:<YOUR_BUILD_DIR>

p.s. for the latest version of training module :ref:`ann_tflow`, please refer to `here <https://ardahsieh.github.io/ANN-tflow-guide/>`_.

Getting Started
===============

1. Prepare the initial structure ...

::

    $ ls
    POSCAR [slamdynk_init_c.sh]

2. Initialize the program

::

    $ bash slamdynk_init_c.sh
