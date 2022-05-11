Installing OpenRCT2 on Linux/BSD
================================

Note: this page is still under construction.

Installing OpenRCT2 itself
--------------------------

OpenRCT2 is in the repositories of several Linux distributions and the ports tree of several BSD flavours. Additionally, there are AppImage and Flatpak builds that work on most Linux distributions. You can also compile the game yourself if you desire.

.. contents::

AppImage (generic Linux)
^^^^^^^^^^^^^^^^^^^^^^^^

You can download the AppImage by going to our official website, https://openrct2.io, and clicking the Download button.

After download, mark the file as executable. You can now start OpenRCT2 by double-clicking it.

You can now proceed to :ref:`Getting the RCT2 files (required)<LinuxBSDGetRCT2>`.

Flatpak (generic Linux)
^^^^^^^^^^^^^^^^^^^^^^^

Go to https://flathub.org/apps/details/io.openrct2.OpenRCT2, click the Install button and follow the on-screen instructions.

You can now proceed to :ref:`Getting the RCT2 files (required)<LinuxBSDGetRCT2>`.

Ubuntu, Linux Mint and derivatives
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

We have provided a PPA for OpenRCT2. These instructions must be executed from a Terminal. You must first pick between release and develop builds.

If you prefer release builds, use this:

``sudo add-apt-repository ppa:openrct2/nightly``

If you prefer develop builds, use this:

``sudo add-apt-repository ppa:openrct2/nightly``

Then, install OpenRCT2:

``sudo apt install openrct2``

If you have a GOG.com version of RCT2 or RCT1, also install ``innoextract``:

``sudo apt install innoextract``

If you have a CD version of RCT2, also install unshield:

``sudo apt install unshield``

You can now proceed to :ref:`Getting the RCT2 files (required)<LinuxBSDGetRCT2>`.

Compiling yourself
^^^^^^^^^^^^^^^^^^

Follow the instructions here: https://github.com/OpenRCT2/OpenRCT2/wiki/Building-OpenRCT2-on-Linux.

.. _LinuxBSDGetRCT2:

Getting the RCT2 files (required)
---------------------------------

We tested several versions of RCT2 and they all work [#f1]_. If you do not yet own RCT2, we recommend that you buy it on https://gog.com. This is because OpenRCT2 can automatically extract the files from the GOG versions, provided the required ``innoextract`` program is installed. (This is bundled with the Flatpak build.)

Getting the RCT1 files (optional, but recommended)
--------------------------------------------------

Extracting the RCT1 files works much the same way as those from RCT2.

.. rubric:: Footnotes

.. [#f1] There are some font issues with the Russian edition. Since OpenRCT2 ships with its own translations and with an extensive font that also contains all the required Russian characters, we strongly recommend installing the English edition of RCT2 even if you want to play in Russian.
