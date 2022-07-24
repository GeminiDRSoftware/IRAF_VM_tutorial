.. _gemvm_shutdown:

Shutting down the VM
********************

* You can shut down the VM by pressing control-c at any time in the terminal
  where ``gemvm`` is running. This does a clean ACPI shutdown (similar to
  pressing the soft power button), but it's best to stop any programs that are
  running first, especially data reduction scripts. If the OS is still booting
  when you press ctrl-c, you will have to wait for that to complete before the
  shutdown starts, after which it should only take a few (~5) seconds.

* Occasionally, if something goes wrong with the boot or shut-down sequence,
  GemVM might time out and return you to the command prompt, with QEMU still
  running as a background process. See :ref:`gemvm_timeouts`.

