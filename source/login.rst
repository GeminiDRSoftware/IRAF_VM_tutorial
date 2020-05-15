.. _login:

Starting the VM & logging in
****************************

* Press the ``Start`` arrow at the top of the ``Oracle VM VirtualBox Manager``
  window to turn on the VM. A console window will open and you will see the
  machine booting in it. You don't need to press anything when the boot menu
  briefly appears. Once the machine has finished booting, you should see a
  "Welcome to the Gemini IRAF VM!" banner with a login prompt underneath.

  .. Initial banner message? No longer appearing.

  .. warning::

      If your mouse pointer stops working, press the left *command* key to
      toggle off mouse/keyboard capture by the VM window.

* Note the password shown in the banner in the console window.

* Minimize the console window, which is only used for controlling the VM and
  not for processing data. The VM has no graphical desktop enviroment and
  graphics are instead displayed to the host desktop using ssh and XQuartz.

* Log in remotely to the VM from one or more terminal window(s).

  - Open a Terminal window (eg. by typing *term* in the ``Launchpad`` search
    box and pressing the Terminal icon).

  .. TO DO

  - Log in to the following fixed IP address with X11 forwarding, using the
    password noted above:

    .. code-block:: none

       ssh -Y irafuser@192.168.56.15

    .. note::

       Use ``-Y``, rather than ``-X``, to help avoid time-outs that cause
       graphics display to stop working.

       There is already an ``~/iraf`` directory with a default ``login.cl`` &
       ``uparm/``.

       The necessary conda environment is activated automatically on login.

