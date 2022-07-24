.. _gemvm_troubleshooting:

Troubleshooting
***************

.. _gemvm_failure_to_start:

Failure to start
================

If ``gemvm``  returns you to the command prompt with an error status almost
immediately, the most likely reasons are:

* The path to the disk image does not exist or is unreadable. The log file will
  have ``Could not open <path>`` (followed by a reason) near the beginning.

  .. To do: Have gemvm check for the existence of the input image(s) and give
     a more explicit error on the terminal?

* The VM image is already running. Either you have ``gemvm`` active in another
  terminal or QEMU has become detached (eg. after a time-out) and is still
  running in the background. The log file will say
  ``Failed to get "write" lock`` and ``Is another process using the image
  [<filename>]?`` at the top. If you can't find an active ``gemvm`` instance,
  try logging into the VM with SSH (:ref:`gemvm_login`) and issue ``sudo
  shutdown now`` when finished. Failing that, see :ref:`gemvm_timeouts` below.

* A large enough block of memory (by default 3GB) could not be allocated.
  GemVM will tell you this and advise you to try re-starting any large
  programs, such as your Web browser, to reduce memory fragmentation and usage.
  On low-memory (eg. 4GB) systems, you might have to keep such programs closed
  while using the VM, but it's more likely that re-starting them will suffice.
  If such errors persist, try reducing the VM's memory allocation (in GB), by
  editing the configuration with ``gemvm-config`` [PENDING] or specifying the
  ``-m`` argument to ``gemvm``. While not optimal, PyRAF can run on CentOS 7
  in as little as 0.5GB, or even 0.25GB with a modest amount of swapping. It is
  inadvisable to try booting with <0.25GB of RAM, which could lead to
  pathologically slow and/or problematic behaviour.

.. _gemvm_timeouts:

Timeouts
========

If something goes wrong with the boot or shut-down sequence (eg. due to
filesystem corruption), GemVM might time out and return you to the command
prompt. In this case, QEMU will probably still be running as a background
process. GemVM will try to print an informative message, including the process
number (if applicable). You can still try logging into the VM (if it has just
taken longer than normal to boot) and issuing ``sudo shutdown now`` as
``irafuser`` once you have finished. If you can't log in, try killing
``qemu-system-x86_64`` with no flags (ie. ``kill <pid>``), which should cause
QEMU to flush its disk buffers before terminating without an error -- that is
not a clean OS shutdown but is the next best thing. If that doesn't stop the
process, you can clean up with ``kill -9 <pid>`` as a last resort.

If the VM persistently fails to boot, a ``--console`` option can be used to see
a boot screen that may provide additional information (please summarize any
errors as accurately as feasible in any helpdesk communications). How this
looks depends on the back-end QEMU capabilities and it might not be visible at
all if you run gemvm remotely.


Helpdesk
========
   
When requesting helpdesk support for problems related to starting, stopping or
logging into the VM, please send ``gemvm_<name>.log``, from the directory where
you run ``gemvm`` (**without** the ``--console`` option). Wait until the
process has stopped before copying the log file.

