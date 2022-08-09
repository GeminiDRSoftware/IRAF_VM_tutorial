.. _gemvm_other:

Other things to know
********************

* While the VM is running idle in the background, it will probably use a few
  percent of a CPU core, which may drain your laptop battery slightly faster
  than usual.

* If you delete or overwrite the qcow2 file, you will lose all the files that
  were on the VM (except those mounted under ``vm_transfer``). To reduce the
  risk of this happening, it is recommended that you keep that disk image in a
  safe location, refer to it using a name defined in your configuration file
  (not by its path) and run gemvm in another directory (such as ~).

* If your disk image (qcow2 file) is readable by other users on the same host
  machine or network filesystem, they will be able to boot a copy and see all
  of the files you have placed on the VM. For that reason, the image is
  distributed in an archive file with restricted read permissions by default.
  Do not let anyone obtain a copy of your disk image if you have installed an
  ssh key that allows you to mount directories from your host machine without
  a password! They will be able to log into your host account.

