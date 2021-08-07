Multiplayer
===========

Multiplayer is a new game mode introduced in OpenRCT2 that allows two or more players to cooperatively play and build on the same park. Similar to games like OpenTTD and MineCraft, a server can be setup which runs a game allowing players to connect to it. When a player joins a server, the park will be downloaded to the client allowing them to play it.

The multiplayer window can be accessed from the main menu screen via the Multiplayer button at the bottom of the screen.

Connecting to a server
----------------------

When you open the multiplayer window you will see a list of public servers and servers you have saved. Type your name or alias into the player name field - this is the name that will be shown to other players in multiplayer games. To connect to a server, click and hold the server you would like to join and then click "Join server" from the popup menu. If the server is password protected you will need to enter in the correct password to join. The park will then be downloaded to your client, this make take a few seconds to a few minutes depending on the speed of the connection from the server to your client and the size of the park.

If you want to join a server that is not advertised on the public server list, you must click the "New server" button and enter the hostname or IP address (and optionally a port if the server is not using the default OpenRCT2 port, 11753). Upon doing this, the server will be saved to your server list so you do not have to type the address in every time you want to join it.

Starting a server 
-----------------

If you want to start a server for your friends to join, you can start a new server from within the game and then immediately play on it. This can be done by clicking "Start Server" and loading a saved game. If you do not want your server to be listed on the public server you must make sure you have the "Advertise" option unchecked.

If you are setting up a public server or are not on the same local area network as your friends - you must make sure that your server can be accessed from outside your local area network. If you are behind a router with Network Address Translation (NAT) enabled (very likely), you must configure your router to forward TCP connections on your chosen port (default is 11753) to your computer. Configuring your router will vary between router brands and will not be covered in this documentation.

Starting a server (Advanced)
----------------------------

OpenRCT2 supports headless mode, useful for dedicated servers. You can enable headless mode by running:

``openrct2 host <saved game path> --headless``

Additional arguments can be used to change the behavior of the server.

======================   =============================  ==================================================
    Argument                 Variable                     Description
======================   =============================  ==================================================
 ``--console``             N/A                             Keeps the console window open (only on Windows)
 ``--headless``            N/A                             Runs OpenRCT2 without graphical interface
 ``--help``                N/A                             Prints out help for CLI 
 ``--port``                Port Number                     Changes the server port number
 ``--user-data-path``      Path to config.ini folder       Changes the server configuration data path
 ``--verbose``             N/A                             Output additional information to the console
======================   =============================  ==================================================

Example (Windows): ``"C:\MyOpenRCTInstall\openrct2.exe" host "C:\MyServerSaves\MyServer.sv6" --port 11753 --headless --console --verbose --user-data-path "E:\MyServerConfig"``

Additional server information can be changed in the ``config.ini`` file. In Windows, by default, this is located under ``"%userprofile%/Documents/OpenRCT2/"``

Starting a server (Windows batch script)
----------------------------

The following batch file (``.bat``) is useful to those that want to host a multiplayer server and ensure that if the OpenRCT2 server crashes it can gracefully restart using the most recent autosave.

Depending on where your OpenRCT2 game is installed, and where your autosave directory is located, you may need to change the variables in lines 3-5 of the script.

To use:
    1. Copy the full content of the script below
    2. Paste into a blank Notepad
    3. Edit the variables on lines 3-5 (as required)
    4. Save the file somewhere easily assessible with the extension ``.bat`` (for example, on your desktop with the name ``Start OpenRCT2 Server.bat``)

Whenever you want to start your server, just run the ``.bat`` file that you saved on step 4.::

    CHCP 65001 >nul
    @echo off
    set OPENRCT2COM=C:\Games\OpenRCT2\openrct2.com
    set USERDATAPATH=%userprofile%\Documents\OpenRCT2
    set AUTOSAVEPATH=%userprofile%\Documents\OpenRCT2\save\autosave
    set PORT=11753
    set PASSWORD=mypasswordhere


    set CONFIGSHOWN=0

    :getautosave
    set NEWESTSAVE=
    cd /d "%AUTOSAVEPATH%"
    for /f "eol=: delims=" %%F in ('dir /b /od *.sv6') do @set "NEWESTSAVE=%%F"
    if %CONFIGSHOWN%==0 goto displayconfig 
    goto restartserver

    :displayconfig
    set PADDED=%OPENRCT2COM%                                                                          .
    set OPENRCT2COMPADDED=%PADDED:~0,74%
    set PADDED=%USERDATAPATH%                                                                          .
    set USERDATAPATHPADDED=%PADDED:~0,74%
    set PADDED=%AUTOSAVEPATH%                                                                          .
    set AUTOSAVEPATHPADDED=%PADDED:~0,74%
    set PADDED=%NEWESTSAVE%                                                                          .
    set AUTOSAVEFILEPADDED=%PADDED:~0,74%
    set PADDED=%PORT%                                                                          .
    set PORTPADDED=%PADDED:~0,74%
    set PADDED=%PASSWORD%                                                                          .
    set PASSWORDPADDED=%PADDED:~0,74%

    echo ╔════════════════════════════════════════════════════════════════════════════╗
    echo ║                     OpenRCT2 Multiplayer Configuration                     ║
    echo ╠════════════════════════════════════════════════════════════════════════════╣
    echo ║                                                                            ║
    echo ║ OpenRCT2.com file:                                                         ║
    echo ║  %OPENRCT2COMPADDED%║
    echo ║ User Data Path:                                                            ║
    echo ║  %USERDATAPATHPADDED%║
    echo ║ Auto Save Path:                                                            ║
    echo ║  %AUTOSAVEPATHPADDED%║
    echo ║ Auto Save File:                                                            ║
    echo ║  %AUTOSAVEFILEPADDED%║
    echo ║ Server Port:                                                               ║
    echo ║  %PORTPADDED%║
    echo ║ Server Password:                                                           ║
    echo ║  %PASSWORDPADDED%║
    echo ║                                                                            ║
    echo ╚════════════════════════════════════════════════════════════════════════════╝
    echo.
    set CONFIGSHOWN=1
    goto startserver

    :startserver
    echo Starting OpenRCT2 multiplayer server...

    :restartserver
    IF "%NEWESTSAVE:~1%"=="~1" (
    echo Starting new map
    "%OPENRCT2COM%" --port %PORT% --user-data-path "%USERDATAPATH%" --password %PASSWORD% --headless
    ) else (
    echo Loading saved game %NEWESTSAVE%
    "%OPENRCT2COM%" host "%AUTOSAVEPATH%\%NEWESTSAVE%" --port %PORT% --user-data-path "%USERDATAPATH%" --password %PASSWORD% --headless
    )
    echo Crash detected. Restarting...
    CHCP 65001 >nul
    goto getautosave
