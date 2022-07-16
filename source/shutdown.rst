.. _gemvm_shutdown:

Shutting down the VM
********************

Other important notes
*********************

* While the VM is running idle in the background, it will probably use a few
  percent of a CPU core, which may drain your laptop battery slightly faster
  than usual.

* If you delete or overwrite the qcow2 file, you will lose all the files that
  were on the VM (except those under the vm_transfer mount). To reduce the risk
  of this happening, it is recommended that you keep that disk image in a safe
  location, refer to it using a name assigned in your configuration file (not
  by its path) and run gemvm in a different directory (such as ~).

