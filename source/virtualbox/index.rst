.. IRAF_VM_tutorial documentation master file, created by
   sphinx-quickstart on Mon Mar 23 22:21:11 2020.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

Old VirtualBox instructions
===========================

These are the "old" instructions from 2020, for Apple machines with an Intel
CPU; they do not work on machines with an M1/M2 (ARM) processor, but you might
find it convenient to continue using this method on older Apple machines.

These instructions are for use with Virtual Box. You may prefer to import the
provided OVA file into some other virtualization software, in which case you
will have to determine how to adapt the following installation and start up
steps accordingly.

An alternative to using Gemini's VM image as described here is to set up your
own virtual machine (`including 32-bit OS libraries <https://astroconda.readthedocs.io/en/latest/faq.html#why-is-iraf-32-bit-instead-of-64-bit>`_)
and install the `Astroconda packages for Python 2
<http://www.gemini.edu/node/11823>`_ on it. This is reportedly easy to do using
`Parallels <https://www.parallels.com>`_ (for a fee).


.. toctree::
   :maxdepth: 2
   :caption: Contents:

   installation
   login
   usage
   shutdown

