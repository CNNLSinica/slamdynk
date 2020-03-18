.. _pylammps:

==============
Using PyLAMMPS
==============

| LAMMPS_ is an open-source code to run classical molecular dynamics simulation for material modeling.
| `PyLAMMPS <https://lammps.sandia.gov/doc/Howto_pylammps.html>`_ is a Python wrapper class which provides an Python interface to execute LAMMPS program.
| Also, PyLAMMPS can run in parallel with mpi4py_, more details please refer to the `official documents`__.

.. _LAMMPS: https://lammps.sandia.gov/
.. _mpi4py: https://mpi4py.readthedocs.io/en/stable/
.. _pylmpmpi: https://lammps.sandia.gov/doc/Howto_pylammps.html#using-pylammps-and-mpi4py-experimental
__ pylmpmpi_

----

Install mpi4py
--------------

[Note] mpi4py and lammps have to use the same MPI.

Method 1. Install with pip

::

 $ pip install mpi4py

Method 2. [recommend] Install with virtualenv or conda, please refer to this `thread <https://lammps.sandia.gov/threads/msg81641.html>`_.

* virtualenv

::

 $ virtualenv myenv
 $ source myenv/bin/activate
 $ pip install mpi4py 

Build LAMMPS
------------

1. Dowload and unpack the package

::

 $ wget https://github.com/lammps/lammps/archive/stable_22Aug2018.tar.gz
 $ tar -xvf stable_22Aug2018.tar.gz
 $ cd stable_22Aug2018

2. Use CMake to `build <https://lammps.sandia.gov/doc/Build_package.html>`_

::

 $ mkdir build
 $ cmake -C ../cmake/presets/std_nolib.cmake -D PYTHON_LIBRARY=/<YOUR_PATH>/lib/libpython<3.x>.so -D PKG_PYTHON=on -D BUILD_LIB=on -D BUILD_SHARED_LIBS=on -D BUILD_MPI=on -D PKG_USER-MEAMC=on -D PKG_MEAM=on -D CMAKE_INSTALL_PREFIX=$VIRTUAL_ENV ../cmake
 $ make -j4

3. Assign the library path before execution

::

 export LD_LIBRARY_PATH=/<YOUR_PATH>/lammps/build/:$LD_LIBRARY_PATH
 export PYTHONPATH=/<YOUR_PATH>/lammps/python/:$PYTHONPATH

