.. _usage:

Using the VM
************

* Start DS9 (or ximtool) & PyRAF in your VM session:

  .. code-block:: none

     ds9 &
     cd iraf
     pyraf
     gemini

* You may then continue processing data as usual. All the IRAF packages from
  Astroconda are available, along with ``emacs`` & ``vi``.

  .. warning::

     When working in the ``/data`` directory shared with the host machine, a
     problem has been observed where certain IRAF tasks (including
     ``gdisplay``) appear to run normally but only process one image extension
     per file, or one of several files, producing incomplete output. You should
     therefore **work in** a directory under ``/home/irafuser`` (so that
     temporary files get written there), but you can still keep input & output
     files on ``/data`` and point the ``rawpath`` parameter of the appropriate
     IRAF tasks there, in order to find them.

* You can also use DRAGONS (and other conda packages), but it is recommended
  that you instead do that directly on the host machine where possible, as you
  are more likely to run into resource limitations on the VM. Only the IRAF
  packages in Astroconda require a 32-bit VM on MacOS >=10.15.

* You should be able to administer the conda packages installed in
  ``/home/irafuser/anaconda2`` as usual. The operating system (CentOS 7)
  installation is **not** intended to be user-maintainable.

