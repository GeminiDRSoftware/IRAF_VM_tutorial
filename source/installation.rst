.. _installation:


Installation & setup
********************

.. TODO

* Download the OVA file with the IRAF VM image from ?? communityCO7.ova.
  A progress bar will be shown under the ``Downloads`` icon in the tray at the
  bottom of the screen.

* Download the DMG file for the free version of Virtual Box from
  https://www.virtualbox.org/wiki/Downloads, under ``OS X hosts``.

* Once the downloads are complete, click on the ``Downloads`` icon and select
  the VirtualBox DMG file to start the installer. Follow the instructions,
  entering your personal password when prompted to do so. Your administrator
  may have to perform this step, if you do not have software installation
  privileges.

* Ensure that you have more than 16GB of available disk space for the VM image
  in your home directory (if necessary, you may reclaim 6GB afterwards by
  deleting the OVA file).

* Start Virtual Box, eg. by going to ``Launchpad`` in the tray at the bottom of
  the screen, typing *virt* in the search box and pressing the VirtualBox icon).

  .. figure:: file_menu.png
     :align: center

     The main VirtualBox Manager window and File menu.

* Go to ``File`` in the menu bar at the top of the screen, then ``Import
  appliance``. Press the icon to the right of the ``File`` box, go to
  ``Downloads`` (or wherever you put the OVA file) and select
  ``communityCO7.ova``. Press ``Continue`` in the main window.

  Alternatively, double clicking on ``communityCO7.ova`` may open it in Virtual
  Box automatically, depending on your settings.

  .. TODO

  - Accept the default settings? Check with Petri.

  - Press ``Import`` and wait for the process to complete.

* Configure networking

  - With the ``Oracle VM VirtualBox Manager`` window selected, go to ``File``
    in the menu bar at the top of the screen and select ``Host Network
    Manager``.

  - Press ``Create`` at the top left of the ``Host Network Manager``
    window. This should automatically add an entry with network address
    ``192.168.15.1/24`` in the table beneath. Leave ``DHCP Server`` de-selected
    and close the window.

* Make sure ``communityCO7`` is selected on the left-hand side of the ``Oracle
  VM VirtualBox Manager`` window.

* Adapt the VM configuration to avoid a bug causing 100% CPU utilization
  (this bullet should go away after IT makes these changes permanent).

  - Disable audio.

  - Enable 3D acceleration.

* Configure a shared data directory.

  - Under your home directory (or another writeable location) on your host
    machine, create a subdirectory for storing data files for use by the VM.

  - In the ``Oracle VM VirtualBox Manager`` window, press ``Settings``, then
    ``Shared Folders`` in the top row of icons, then the ``+`` icon to the
    right of the main table. In the sub-window that pops up, set the ``Folder
    Path`` to the directory you created on the host machine
    (eg. ``/Users/<username>/vm_data``) and the ``Mount Point`` to ``/data``.
    Select the ``Auto-mount`` option (and ``Make Permanent``, if you have it).
    Press ``OK`` and then ``OK`` again in the parent window.

    .. Where did the "Make Permanent" option go?  TO DO

