.. IRAF_VM_tutorial documentation master file, created by
   sphinx-quickstart on Mon Mar 23 22:21:11 2020.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

Gemini IRAF VM tutorial
=======================

Instructions for running Astroconda (32-bit) IRAF under an Intel Linux virtual
machine on MacOS 10.15 or later.

A link to the previous instructions for VirtualBox can be found below, but they
do **not** work on newer M1/M2 (ARM) Apple machines, nor can VMWare or
Parallels run Gemini IRAF on those machines.

.. These newer instructions describe the method now recommended for *all* Apple
   hardware; nevertheless, an updated OVA file has been made available for
   anyone that wishes to continue using VirtualBox on Intel for the time being.

This method uses `QEMU <https://www.qemu.org>`_ to emulate Intel hardware on
ARM64, which works well, producing the same results as on a Linux machine, but
with a large performance penalty. A test case using GMOS multi-slit data took
**14 times** as long to run on an M1 machine as when running Linux natively on
a recent i7 processor, with the overhead varying considerably between different
processing steps. This is, however, the *only* way of running the necessary
IRAF packages on new Apple CPUs (at least prior to *possible* optimizations in
MacOS 13).

.. On Apple machines with Intel processors, the virtualization overhead is much
   smaller and the processing speed should be similar to that on VirtualBox.

Compared with the original version 1 release for VirtualBox, the new Gemini
IRAF VM image has the following features:

  * A new control interface, GemVM.
  * A simpler installation method, using Anaconda / Miniconda.
  * The latest Gemini IRAF 1.15.
  * The latest DRAGONS 3.0.3. [#f1]_
  * A new version of PyRAF (2.2.1) that is fully compatible with Python 3.
  * More recent Anaconda (2021.11) package versions.
  * The (unofficial) PyFU scripts for mosaicking IFU datacubes.
  * Support for compiling IRAF packages.
  * Miscellaneous OS updates etc.

.. toctree::
   :maxdepth: 2
   :caption: Contents:

   installation
   login
   usage
   shutdown
   virtualbox/index

.. [#f1] (You should run DRAGONS directly on your host machine instead, unless
         you really need to use it in conjunction with IRAF.)
