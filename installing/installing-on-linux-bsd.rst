Installing OpenRCT2 on Linux/BSD
================================

Installing
----------

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

If you have a CD version of RCT2, install ``unshield``. Also make sure that you have Zenity or Kdialog installed. (Most Linux distributions have it preinstalled, especially if you have GNOME or KDE installed.) 

You can now proceed to :ref:`Getting the RCT2 files (required)<LinuxBSDGetRCT2>`.

Ubuntu, Linux Mint and derivatives
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

We have provided a PPA for OpenRCT2. These instructions must be executed from a Terminal. You must first pick between release and develop builds.

If you prefer release builds, use this::

    sudo add-apt-repository ppa:openrct2/master

If you prefer develop builds, use this::

    sudo add-apt-repository ppa:openrct2/nightly

Then, install OpenRCT2::

    sudo apt install openrct2

If you have a GOG.com version of RCT2 or RCT1, also install ``innoextract``::

    sudo apt install innoextract

If you have a CD version of RCT2, also install ``unshield``::

    sudo apt install unshield

You can now proceed to :ref:`Getting the RCT2 files (required)<LinuxBSDGetRCT2>`.

Debian
^^^^^^

OpenRCT2 is in the Debian repositories as of Bookworm, released in 2023. You can install it with::

    sudo apt install openrct2

Also note that Debian has the game-data-packager, which can help you extract the RCT2 files more easily. OpenRCT2
will automatically look in the appropriate directories. This is however, not fully documented yet.

Also keep these things in mind:

1. Debian removes a few objects, so some parks may not load. You can however take these from a ZIP build of OpenRCT2 and
   add them to your custom content folder, or switch a build that is directly supplied by OpenRCT2 instead.
2. Debian does not update its OpenRCT2 package. To get around this, you can either enable the backports repository or
   use one of the other options instead.

If the repository version of OpenRCT2 is not a good fit, you can still use the Launcher or AppImage builds,
or just compile OpenRCT2 yourself.

Arch Linux
^^^^^^^^^^

If you want the release build (some servers use these), install the standard `openrct2 <https://archlinux.org/packages/community/x86_64/openrct2/>`_ package::

    sudo pacman -S openrct2

Alternatively, if you want the latest development build, install the -git package from the `AUR <https://aur.archlinux.org/>`_. The dev builds are analogous to beta versions - they should work, but don't expect everything to be perfect.
::

    git clone https://aur.archlinux.org/openrct2-git.git
    cd openrct2-git
    makepkg -si

If you have a GOG.com version of RCT2 or RCT1, also install ``innoextract``::

    sudo pacman -S innoextract

If you have a CD version of RCT2, also install ``unshield``::

    sudo pacman -S unshield

You can now proceed to :ref:`Getting the RCT2 files (required)<LinuxBSDGetRCT2>`.

OpenSUSE
^^^^^^^^

You can obtain the latest release or develop version of OpenRCT2 from the `OBS <https://build.opensuse.org/package/show/games/openrct2>`_::

    sudo zypper install openrct2

If you have a GOG.com version of RCT2 or RCT1, also install ``innoextract``::

    sudo zypper install innoextract

If you have a CD version of RCT2, also install ``unshield``::

    sudo zypper install unshield

You can now proceed to :ref:`Getting the RCT2 files (required)<LinuxBSDGetRCT2>`.

Gentoo
^^^^^^

Accept ~amd64 (or equivalent for your arch) for the openrct2 package, add this to /etc/portage/package.accept_keywords/openrct2 (for example)::

    games-simulation/openrct2 ~amd64

Alternatively, if you want the latest development build, use the live ebuild. The live ebuild will compile the latest dev version, and although they should work, it may not always compile (when upstream build has changed but the ebuild hasn't caught up yet).
::

    =games-simulation/openrct2-9999 **
    
And then install the package::

    sudo emerge --ask --verbose openrct2

If you have a GOG.com version of RCT2 or RCT1, install ``innoextract``. If you have a CD version of RCT2, install ``unshield``. Also make sure that you have Zenity or Kdialog installed.

You can now proceed to :ref:`Getting the RCT2 files (required)<LinuxBSDGetRCT2>`.

Fedora
^^^^^^

You will need the dependencies to build the game - there is no package for the game as of yet::

    sudo dnf install gcc gcc-c++ json-devel \
    openssl-devel SDL2-devel libicu-devel \
    speexdsp-devel libcurl-devel libzstd-devel \
    cmake fontconfig-devel freetype-devel \
    libpng-devel libzip-devel mesa-libGL-devel \
    duktape-devel flac-devel libvorbis-devel

Build the game::

    git clone https://github.com/OpenRCT2/OpenRCT2.git && cd ./OpenRCT2 && mkdir build && cd build && cmake -DCMAKE_BUILD_TYPE=Release ../ && make

Set up the files::

    cp -r ../data/ ./data/ && make graphics && mv ./g2.dat ./data/g2.dat

If you do not run the following command, then assets are not downloaded, and libraries are not put where they need to go. The app will start, but will have no assets. Sudo is needed to put assets in /usr and /lib.
::

    sudo make install

You can now proceed to :ref:`Getting the RCT2 files (required)<LinuxBSDGetRCT2>`.

NixOS
^^^^^

The installation is currently based on your nixpkgs-channel. If you're using the unstable channel, just install the package::

    nix-env -iA nixos.openrct2
    
If you're on an stable channel (like 17.09 or older) you can install this single package from the unstable channel::
    
    nix-env -f https://github.com/NixOS/nixpkgs-channels/archive/nixos-unstable.tar.gz -iA openrct2
    
Alternatively you can build the `expression <https://github.com/NixOS/nixpkgs/blob/master/pkgs/games/openrct2/default.nix>`_ from the nixpkgs.

You can now proceed to :ref:`Getting the RCT2 files (required)<LinuxBSDGetRCT2>`.

Compiling yourself
^^^^^^^^^^^^^^^^^^

Follow the instructions here: https://github.com/OpenRCT2/OpenRCT2/wiki/Building-OpenRCT2-on-Linux.

.. _LinuxBSDGetRCT2:

If you have a GOG.com version of RCT2 or RCT1, install ``innoextract``. If you have a CD version of RCT2, install ``unshield``.

Getting the RCT2 files (required)
---------------------------------

We tested several versions of RCT2 and they all work. If you do not yet own RCT2, we recommend that you buy it on https://gog.com. This is because OpenRCT2 can automatically extract the files from the GOG versions, provided the required ``innoextract`` program is installed. (This is bundled with the Flatpak build.)

Steam
^^^^^

Since RollerCoaster Tycoon 2 is a Windows game, you must first enable Steam Play if you haven’t done so already. To do this, use the menus: :menuselection:`Steam --> Settings --> Steam Play` and tick the options ``Enable Steam Play for supported titles`` and ``Enable Steam Play for all other titles``.

With Steam Play enabled, the Install button should now be enabled. Click it. Once this is done, you can now start OpenRCT2. If asked to provide the location of the files, select ``I have already installed RollerCoaster Tycoon 2``. A directory browser will now open. Point it to the location of the installed files (which can be found by clicking :menuselection:`Settings (cog) --> Properties --> Installed Files --> Browse` from the game page within ths Steam Library). Typical locations include:
- ``/home/<username>/.local/share/Steam/steamapps/common/Rollercoaster Tycoon 2``
- ``/home/<username>/.local/share/Steam/steamapps/common/RollerCoaster Tycoon Classic``
- ``/home/<username>/snap/steam/common/.local/share/Steam/steamapps/common/Rollercoaster Tycoon 2``
- ``/home/<username>/snap/steam/common/.local/share/Steam/steamapps/common/RollerCoaster Tycoon Classic``

GOG.com
^^^^^^^

You will need to use the offline installer for the game, the default GOG Galaxy installer will not work with this method.

On gog.com, open your library. Hover over the thumbnail of RCT2 and a button with an arrow will appear. Click it, then select ``View Downloads``. At the bottom of the pop-up there will be a section called “Download offline backup game installers”.
There are two files you need to download, a 1 MB .exe file and a 553 MB .bin file, labelled ‘Part 1 of 2’ and ‘Part 2 of 2’. You can click on them to download. Make sure you download both files to the same directory.

Once this is done, you can now start OpenRCT2. You will be asked to provide the location of your files. Select ``I have downloaded the offline GOG installer for RollerCoaster Tycoon 2, but I haven’t installed it yet``. A file picker will open, simply point it to the .exe file you just downloaded and OpenRCT2 should take care of the rest for you.

Getting the RCT1 files (optional, but recommended)
--------------------------------------------------

Depending on your situation, your RCT1 install may be autodetected. If not, you will have provide a location manually.

Extracting the RCT1 files works much the same way as those from RCT2.

Steam
^^^^^

Since RollerCoaster Tycoon 1 is a Windows game, you must first enable Steam Play if you haven’t done so already. To do this, use the menus: :menuselection:`Steam --> Settings --> Steam Play` and tick the options ``Enable Steam Play for supported titles`` and ``Enable Steam Play for all other titles``.

With Steam Play enabled, the Install button should now be enabled. Click it. Once this is done, you can now link to it from OpenRCT2. To do this, start OpenRCT2, click ``Options`` and navigate to the tab with the wrench. On the top of that tab is a widget that you can click to set the directory. A directory browser will now open. Point it to ``/home/<username>/.local/share/Steam/steamapps/common/RollerCoaster Tycoon Deluxe``.

GOG
^^^

First, install the ``innoextract`` package. See the earlier paragraphs for distribution-specific instructions if needed.

You will need to use the offline installer for the game, the default GOG Galaxy installer will not work with this method.

On gog.com, open your library. Hover over the thumbnail of RCT Deluxe and a button with an arrow will appear. Click it, then select ``View Downloads``. At the bottom of the pop-up there will be a section called “Download offline backup game installers”. Download the .exe file listed here.

Afterwards, open a terminal and execute the following command:

    innoextract <path to downloaded .exe>

Once this is done, you can now link to it from OpenRCT2. To do this, start OpenRCT2, click ``Options`` and navigate to the tab with the wrench. On the top of that tab is a widget that you can click to set the directory. A directory browser will now open. Point it to the folder where ``rct.exe`` resides.

Setting an RCT2 path without Zenity or Kdialog
----------------------------------------------

When OpenRCT2 first launches, you will be prompted to select the directory where you installed RCT2. This requires either Zenity or Kdialog to be installed.

You can also set the RCT2 path from the command line should you wish::

    openrct2 set-rct2 /path/to/rct2-install
