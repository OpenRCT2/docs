Installing OpenRCT2 on macOS
============================

Getting the RCT2 files (required)
---------------------------------

In order to run, OpenRCT2 will need some files from RollerCoaster Tycoon 2. The best method will depend on your situation:

From a Windows machine/copied install
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

If you have a Windows machine at hand, you can simply install it and then copy the ``RollerCoaster Tycoon 2`` folder to your Mac. It does not matter where you place this folder, but keep a note where you put it, as OpenRCT2 will ask for this location when it starts for the first time.

From a GOG.com offline installer
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

You will need to use the offline installer for the game, the default GOG Galaxy installer will not work with this method.

On gog.com, open your library. Hover over the thumbnail of RCT2 and a button with an arrow will appear. Click it, then select ``View Downloads``. At the bottom of the pop-up there will be a section called “Download offline backup game installers”. Click the line under that and the installer will be downloaded.

Then, get this utility called Extractor: https://macsourceports.com/utility/extractor . Use the to extract the contents of the downloaded file somewhere you like. Keep a note of where you extracted it.

Once this is done, you can now start OpenRCT2. A file picker will open, direct to the directory where you extracted that GOG installer (hint: this directory will contain the rct2.exe file) and OpenRCT2 should now work.

Steam
^^^^^
Launch Steam with the console enabled::

    /Applications/Steam.app/Contents/MacOS/steam_osx -console

You should now see additional tab in the top menu called CONSOLE. Open it, and enter the following command::

    download_depot 285330 285331

If you also own RCT1 Deluxe on Steam and want those assets as well, you could enter this command. You don’t have to wait for the first download to finish before entering the second one.
::

    download_depot 285310 285311

Once the download is complete, the console will display something along the lines of::

    Depot download complete : /Users/<username>/Library/Application Support/Steam/steamapps/content/app_285330/depot_285331

The game won’t show up in the ‘installed’ list - this is normal.

From a CD (Wine)
^^^^^^^^^^^^^^^^

You can use WINE - a reimplementation of the Windows API - to run the installer. Using a wrapper such as `PlayOnMac <https://www.playonmac.com/>`_ is recommended to make the process easier. Follow the wizard the wrapper provides, pointing it to the installer at the appropriate point. It does not matter if RCT2 actually runs, as we'll be using the OpenRCT2 application.

After installing, you need to copy the files of RCT2 to an easy-to-find location. In PlayOnMac, this can be done by highlighting the installed game, clicking “Open folder” and copying the contents of that folder somewhere. Remember the location, as OpenRCT2 will ask for it later on.

From a CD (unshield)
^^^^^^^^^^^^^^^^^^^^

If using Wine is not option, you can use the unshield tool. This tool can be installed via `MacPorts <https://www.macports.org/>`_::

    sudo port install unshield    

or `Brew <https://brew.sh/>`_::

    brew install unshield

Now, extract the contents of the CD (substituting EXTRACTDIR and INSTALLER-LOCATION)::

    unshield -g Minimum -d "$EXTRACTDIR" x "$INSTALLER-LOCATION/data1.hdr"
    cp -R "$INSTALLER-LOCATION/Data/" "$EXTRACTDIR/Minimum/Data"
    mv "$EXTRACTDIR/Minimum" "$EXTRACTDIR/RCT2"
    
If you have CDs for Wacky Worlds and/or Time Twister, repeat this step with the CDs in question.

Getting the RCT1 files (optional)
---------------------------------

Optionally, you can also add the RCT1 files. Extracting these works much the same as extracting RCT2. Using these files requires linking OpenRCT2 to it. The instructions to do so are linked at the end of this article.

Installing OpenRCT2 itself
--------------------------

To install OpenRCT2 on macOS, go to https://openrct2.io/ and download either the latest release or a development build. The builds are packages in a ZIP file. Extract it, then drag OpenRCT2.app to Applications.

Running OpenRCT2
----------------

Once you installed OpenRCT2 and copied the necessary RCT2 files, you can attempt to run it. Most likely, macOS will not run the application, as it does not recognise it. You can whitelist the application by opening System Preferences, navigating to “Security & Privacy” and clicking “Open Anyway”.

Other options
-------------

You have now set up the basic install. Depending on your situation, there is one more possibility to improve your install.

.. toctree::
   :titlesonly:

   linking-to-rct1
