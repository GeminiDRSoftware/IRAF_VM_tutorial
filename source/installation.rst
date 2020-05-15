.. _installation:


Installation & setup
********************

.. |ova_file| raw:: html

   <a href="https://drive.google.com/file/d/1vRAPmdPdH25Sn4gkjZ7AmTHIL6FM0NeG/view?usp=sharing" target="_blank">Google Drive</a>

.. |vbox_downloads| raw:: html

   <a href="https://www.virtualbox.org/wiki/Downloads" target="_blank">https://www.virtualbox.org/wiki/Downloads</a>


* Get the installation files

  - Download the OVA file containing the IRAF VM image
    (``gemini-IRAF-CO7.ova``) from |ova_file|. This is 6GB in size, so will
    take a while to transfer.

  - To ensure the integrity of the download, you can open a terminal
    window (see :ref:`login`), type ``shasum Downloads/gemini-IRAF-CO7.ova``
    (substituting whatever path you downloaded it to) and verify that the
    resulting checksum is ``1881ae0afa3e9699ccec861b508a630787cf566d``; if not,
    you should try downloading again.

  - Download the DMG file for the free version of Virtual Box from
    |vbox_downloads|, under ``OS X hosts``. A checksum is also available on
    that page, which you can verify using ``shasum -a 256 filename.dmg``.

* Install Virtual Box

  - Once the downloads are complete, go to ``Downloads`` and select the
    VirtualBox DMG file to start the installer. Follow the instructions,
    entering your personal password when prompted to do so. Your administrator
    may have to perform this step, if you do not have software installation
    privileges.

* Import the VM image

  - Ensure that you have more than 16GB of available disk space for the VM
    image in your home directory (if necessary, you may reclaim 6GB afterwards
    by deleting the OVA file).

  - Start the "VirtualBox" application.

    .. figure:: file_menu.png
       :align: center

       The main VirtualBox Manager window and File menu.

  - Go to ``File`` in the menu bar at the top of the screen, then ``Import
    appliance``. Press the icon to the right of the ``File`` box, go to
    ``Downloads`` (or wherever you put the OVA file) and select
    ``gemini-IRAF-CO7.ova``. Press ``Continue`` in the main window.

    Alternatively, double clicking on ``gemini-IRAF-CO7.ova`` may open it in
    Virtual Box automatically, depending on your settings.

    - Accept the default settings.

    - Press ``Import`` and wait for the process to complete.

* Configure networking

  - With the ``Oracle VM VirtualBox Manager`` window selected, go to ``File``
    in the menu bar at the top of the screen and select ``Host Network
    Manager``.

  - Press ``Create`` at the top left of the ``Host Network Manager``
    window. This should automatically add an entry with network address
    ``192.168.56.1/24`` in the table beneath. Don't enable ``DHCP Server``
    (unless you're already using it for another purpose). Close the window.

* Make sure ``gemini-IRAF-CO7`` is selected on the left-hand side of the
  ``Oracle VM VirtualBox Manager`` window.

* Configure a shared data directory.

  - Under your home directory (or another writeable location) on your host
    machine, create a subdirectory for exchanging data files between the host
    and the VM, eg. ``vm_transfer/``.

  - In the ``Oracle VM VirtualBox Manager`` window, press ``Settings``, then
    ``Shared Folders`` in the top row of icons, then the ``+`` icon to the
    right of the main table. In the sub-window that pops up, set the ``Folder
    Path`` to the directory you created on the host machine
    (eg. ``/Users/<username>/vm_transfer``) and the ``Mount Point`` to
    ``/home/irafuser/vm_transfer`` (or similar). Select the ``Auto-mount``
    option (and ``Make Permanent``, if you have it). Press ``OK`` and then
    ``OK`` again in the parent window.

    .. Where did the "Make Permanent" option go?

