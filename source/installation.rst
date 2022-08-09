.. _gemvm_installation:

Installation & setup
********************

.. |disk_image| raw:: html

   <a href="https://drive.google.com/file/d/17rswmFMIJF7toWUt2ezcdwA3h3D5va6r/view?usp=sharing" target="_blank">Google Drive</a>

.. |anaconda_downloads| raw:: html

   <a href="https://www.anaconda.com/products/distribution" target="_blank">anaconda.com</a>

.. |anaconda_terms| raw:: html

   <a href="https://www.anaconda.com/terms-of-service" target="_blank">terms of service</a>

.. |dragons_install| raw:: html

   <a href="http://www.gemini.edu/observing/phase-iii/understanding-and-processing-data/data-processing-software/download-latest" target="_blank">DRAGONS installation</a>


Get the installation files
==========================

* Download the IRAF VM disk image file (``gemini-IRAF-CO7-2022.07.zip``)
  from |disk_image|. This is 5GB in size, so will take a while to transfer.

  - If you're using Apple's Safari Web browser, it will probably unzip the file
    for you automatically. Otherwise, you can open a terminal window, go to the
    directory where the file was downloaded (usually ``cd Downloads``) and type
    ``unzip gemini-IRAF-CO7-2022.07.zip`` (or use another archive manager) to
    extract it.

  - To ensure the integrity of the download, type
    ``shasum gemini-IRAF-CO7-2022.07.qcow2`` and verify that the resulting
    checksum is ``932d9db4224429cb326bfe969253ec9e75253dcc``; if not, you
    should try downloading again.

* If you don't already have Anaconda installed on your host machine,
  download it from |anaconda_downloads| (noting the non-commercial
  |anaconda_terms| for their repository). You may use Miniconda if you prefer.

  .. warning::

     You should normally download Anaconda's "64-Bit Command Line Installer"
     for Intel, **even on Apple M1/M2 (ARM64) machines**, *not* the "64-Bit
     (M1)" installer.

     Anaconda's new M1 installer *can* be used, but there is no DRAGONS build
     for it yet (as of mid 2022), which is needed for reducing Gemini imaging
     (and eventually spectroscopic) data in Python. In the meantime, a small
     M1-native enviroment can be created within the Intel/MacOS version of
     Anaconda, allowing the IRAF VM to coexist easily with DRAGONS.


Set up Anaconda on your host machine
====================================

If you haven't already done so, you should install Anaconda as for
|dragons_install| (or following Anaconda's instructions). Make sure that the
necessary conda channels are defined, as in the section "Set up Anaconda
Channels" of that page. It is not obligatory to install DRAGONS itself. Don't
install Gemini IRAF, since that's provided by the VM (on MacOS 10.15+).

.. _gemvm_install_cmd:

Install GemVM
=============

With the Anaconda base environment activated (type ``conda activate``) and
Gemini's public conda channel defined (see the DRAGONS link above), issue the
following command to install GemVM and its dependencies:

Apple M1/M2 (ARM64) host machines:
  .. code-block:: none

     CONDA_SUBDIR=osx-arm64 conda create -n gemvm gemvm

Intel host machines:
  .. code-block:: none

     conda create -n gemvm gemvm


.. _gemvm_setup:

Set up the VM
=============

* Place the VM disk image that you downloaded earlier in a safe, permanent
  location (such as ``~/GemVM/``). If anything happens to this file, you will
  lose the entire contents of the VM. The file will initially occupy 14GB of
  disk space, growing to a maximum of 50GB as you create data files on the VM.

* Run ``gemvm-config`` to assign a name/label (and any other parameters you
  want to tweak) to the downloaded VM image, eg.:

  .. code-block:: none

     conda activate gemvm
     gemvm-config add IRAF-2022.07 ~/GemVM/gemini-IRAF-CO7-2022.07.qcow2

  where ``IRAF-2022.07`` is the name you wish to use. Referring to the VM image
  by an assigned name is both more convenient and safer than typing the file
  path every time, since it's easy to work in another directory, with less risk
  of inadvertently deleting the image.

