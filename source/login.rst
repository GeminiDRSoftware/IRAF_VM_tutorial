.. _gemvm_login:

Starting the VM & logging in
****************************

* Make sure the appropriate conda environment is activated in your terminal
  window:

  .. code-block:: none

     conda activate gemvm

* Start the VM as follows:

  .. code-block:: none

     gemvm IRAF-2022.07

  (where ``IRAF-2022.07`` is whatever name you assigned to the VM in
  :ref:`gemvm_setup`).

  For additional options, refer to the help output from ``gemvm -h``.

  The status shown in the terminal will change from "booting" to "running"
  once the VM is ready to log into (which should take less than a minute).
  See :ref:`gemvm_troubleshooting` if that doesn't happen.

  .. figure:: GemVM.png
     :align: center

     The GemVM control screen, running in a terminal window.

  If there is not a large enough block of memory available (3GB by default),
  GemVM will ask you to try re-starting any large programs, such as your Web
  browser; see :ref:`gemvm_failure_to_start`.

* Log in "remotely" to the VM with X11 forwarding, by typing the following
  command in at least one other terminal window:

  .. code-block:: none

     ssh -Y -p 2222 irafuser@localhost

  The port number (2222) might vary if you override it. The password should
  appear above the login prompt and is unchanged from the previous (VirtualBox)
  version of the VM.

  .. note::

     Use ``-Y``, rather than ``-X``, to help avoid time-outs that can cause
     graphics display to stop working.

