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

After download, mark the file as executable. OpenRCT2 can now be run by double-clicking it. (Don’t run it just yet—you need to install RCT2 first.)

If you have a GOG.com version of RCT2 or RCT1, install ``innoextract``. If you have a CD version of RCT2, install ``unshield``. Also make sure that you have Zenity or Kdialog installed. (Most Linux distributions have it preinstalled, especially if you have GNOME or KDE installed.) 

You can now proceed to :ref:`Getting the RCT2 files (required)<LinuxBSDGetRCT2>`.

Flatpak (generic Linux)
^^^^^^^^^^^^^^^^^^^^^^^

Go to https://flathub.org/apps/details/io.openrct2.OpenRCT2, click the Install button and follow the on-screen instructions.

If you have a GOG.com version of RCT2 or RCT1, install ``innoextract``. If you have a CD version of RCT2, install ``unshield``. Also make sure that you have Zenity or Kdialog installed. (Most Linux distributions have it preinstalled, especially if you have GNOME or KDE installed.) 

You can now proceed to :ref:`Getting the RCT2 files (required)<LinuxBSDGetRCT2>`.

Ubuntu, Linux Mint and derivatives
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

We have provided a PPA for OpenRCT2. These instructions must be executed from a Terminal. You must first pick between release and develop builds.

If you prefer release builds, use this:
``sudo add-apt-repository ppa:openrct2/master``

If you prefer develop builds, use this:
``sudo add-apt-repository ppa:openrct2/nightly``

Then, install OpenRCT2:
``sudo apt install openrct2``

If you have a GOG.com version of RCT2 or RCT1, also install ``innoextract``:
``sudo apt install innoextract``

If you have a CD version of RCT2, also install ``unshield``:
``sudo apt install unshield``

You can now proceed to :ref:`Getting the RCT2 files (required)<LinuxBSDGetRCT2>`.

Compiling yourself
^^^^^^^^^^^^^^^^^^

Follow the instructions here: https://github.com/OpenRCT2/OpenRCT2/wiki/Building-OpenRCT2-on-Linux.

.. _LinuxBSDGetRCT2:

Getting the RCT2 files (required)
---------------------------------

We tested several versions of RCT2 and they all work [#f1]_. If you do not yet own RCT2, we recommend that you buy it on https://gog.com. This is because OpenRCT2 can automatically extract the files from the GOG versions, provided the required ``innoextract`` program is installed. (This is bundled with the Flatpak build.)

Steam
^^^^^

Since RollerCoaster Tycoon 2 is a Windows game, you must first enable Steam Play if you haven’t done so already. To do this, use the menus: :menuselection:`Steam --> Settings --> Steam Play` and tick the options ``Enable Steam Play for supported titles`` and ``Enable Steam Play for all other titles``.

With Steam Play enabled, the Install button should now be enabled. Click it. Once this is done, you can now start OpenRCT2. If asked to provide the location of the files, select ``I have already installed RollerCoaster Tycoon 2``. A directory browser will now open. Point it to ``/home/<username>/.local/share/Steam/steamapps/common/Rollercoaster Tycoon 2``. 

GOG.com
^^^^^^^

You will need to use the offline installer for the game, the default GOG Galaxy installer will not work with this method.

On gog.com, open your library. Hover over the thumbnail of RCT2 and a button with an arrow will appear. Click it, then select ``View Downloads``. At the bottom of the pop-up there will be a section called “Download offline backup game installers”. Click the line under that and the installer will be downloaded.

Once this is done, you can now start OpenRCT2. You will be asked to provide the location of your files. Select ``I have downloaded the offline GOG installer for RollerCoaster Tycoon 2, but I haven’t installed it yet``. A file picker will open, simply point it to the file you just downloaded and OpenRCT2 should take care of the rest for you.

Getting the RCT1 files (optional, but recommended)
--------------------------------------------------

Extracting the RCT1 files works much the same way as those from RCT2.

Steam
^^^^^

Since RollerCoaster Tycoon 1 is a Windows game, you must first enable Steam Play if you haven’t done so already. To do this, use the menus: :menuselection:`Steam --> Settings --> Steam Play` and tick the options ``Enable Steam Play for supported titles`` and ``Enable Steam Play for all other titles``.

With Steam Play enabled, the Install button should now be enabled. Click it. Once this is done, you can now link to it from OpenRCT2. To do this, start OpenRCT2, click ``Options`` and navigate to the tab with the wrench. On the bottom of that tab is a widget that you can click to set the directory. A directory browser will now open. Point it to ``/home/<username>/.local/share/Steam/steamapps/common/RollerCoaster Tycoon Deluxe``.

.. rubric:: Footnotes

.. [#f1] There are some font issues with the Russian edition. Since OpenRCT2 ships with its own translations and with an extensive font that also contains all the required Russian characters, we strongly recommend installing the English edition of RCT2 even if you want to play in Russian.
