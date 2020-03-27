.. _login:

Starting the VM & logging in
****************************

* Press the ``Start`` arrow in the ``Oracle VM VirtualBox Manager`` window to
  turn on the VM. Wait for it to boot. A console window will open. You don't
  need to press anything when the boot menu briefly appears. When the machine
  has finished booting, you should see a login prompt.

.. Initial banner message? No longer appearing.

.. warning::

    If your mouse pointer stops working, press the left *command* key to
    toggle off mouse/keyboard capture by the VM window.

* Minimize the console window, which is only used for controlling the VM and
  not for processing data. The VM has no graphical desktop enviroment and
  graphics are instead displayed to the host desktop using ssh and XQuartz.

* Log in remotely to the VM from one or more terminal window(s).

  - Open a Terminal window (eg. by going to ``Launchpad`` in the tray at the
    bottom of the screen, typing *term* in the search box and pressing the
    Terminal icon).

  .. TO DO

  - Log in to the following fixed IP address with X11 forwarding, using the
    password "TBC":

    .. code-block:: none

       ssh -Y irafuser@192.168.56.15

    .. note::

       Use -Y, rather than -X, to help avoid time-outs that cause graphics
       display to stop working.

       There is already an ~/iraf directory with a default login.cl & uparm.

       The necessary conda environment is activated automatically on login.

