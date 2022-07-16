.. _shutdown:

Shutting down the VM
********************

* You can shut down the VM by clicking the close button (|close_button|) on the
  upper left of the console window, or from ``Machine`` in the menu bar. To
  shut it down completely, you can choose ``Send the shutdown signal`` / ``ACPI
  shutdown``, or you can ``Save the machine state`` to resume later where you
  left off.

  .. |close_button| image:: close_button.png
     :scale: 75


Other important notes
*********************

* While the VM is running idle in the background, it will probably use a
  few percent of a CPU core, which may drain your laptop battery faster
  than usual.

* If you delete the VM, you will likely lose all the files that were on it
  (except those in the shared directory).

* Make sure you have read the warning about not working directly in the
  ``vm_transfer`` directory under :ref:`usage`.

