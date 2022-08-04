.. _gemvm_usage:

Using the VM
************

* The VM comes with an ``~/iraf`` directory, containing a default ``login.cl``
  & ``uparm/``.

* The ``geminiconda`` environment is activated automatically on login.

* Start DS9 (or XImtool) and PyRAF in your VM session:

  .. code-block:: none

     ds9 &
     cd iraf
     pyraf
     gemini

* You may then continue processing data as usual. All the IRAF packages from
  Astroconda are available, along with ``emacs`` & ``vi``.

* You can also use DRAGONS (and other conda packages), but it's better to run
  those directly on the host machine wherever possible, since processing data
  on non-x86 machines is an order of magnitude slower when using the VM and you
  are more likely to run into resource limitations there. Only the IRAF
  packages *require* a VM on MacOS.

* You can administer the conda packages in ``/home/irafuser/miniconda3`` as
  usual, though conda commands might take some minutes to run on the VM. The
  operating system (CentOS 7) installation is **not** intended to be
  user-maintainable.

* It should be possible to leave the VM running while your laptop is suspended
  and resume processing later -- but you may find that the clock time is wrong
  on the VM afterwards. There is currently no way to suspend the VM itself.

