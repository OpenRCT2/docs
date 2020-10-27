Options
=======

There are a number of options for OpenRCT2 that can be tuned to fit your preferences and needs. They are broken up into a number of different sections.

Display
-------

There are a number of options dedicated to how the game runs on your screen.

* **Screen mode**

  Can be one of three values:

  * *Windowed* - the game will run inside a window with standard decorations like minimize and close buttons.
  * *Fullscreen* - the game is allowed to take over the screen output, allowing the game to achieve better performance than Fullscreen (borderless window). Switching to and from the window (such as through Alt+Tab) will cause a short delay.

    * When Fullscreen is selected, you can also select the Display Resolution the game should run at. The options available depend on your monitor.

  * *Fullscreen (borderless window)* - exactly like Windowed, but with no window decorations, allowing the game to take up the entire screen space.

* **Window scale factor**

  Determines the scale the game will be rendered at. At ``1.00`` scale factor, the game runs at its original scale of 1 game pixel to 1 screen pixel. This setting is useful for larger resolutions, where this scale makes the UI extremely small and otherwise unusable. At non-integer values, this enables the *Scaling quality* setting below.

* **Drawing Engine**

  Can be one of three values:

  * *Software* - the game uses a software renderer based on the CPU to render and draw the game.
  * *Software (hardware display)* - the game uses a software renderer based on the CPU to render the game, while it uses the hardware device to draw the rendered image to the screen.
  * *OpenGL (experimental)* - the game uses OpenGL to render and draw the game.

  Selecting a hardware renderer (*Software (hardware display)* or *OpenGL*) enables **Scaling quality** if the **Window scale factor** is not an integer, **Pause game when Steam overlay is open**, and **Use vertical sync**.

  * **Scaling Quality**

    Requires a hardware renderer. Can be one of two values:

    * *Linear* - Scaling is smooth, but blurry.
    * *Smooth Nearest Neighbour* - Scaling is sharp but takes a bit more performance.

    .. figure:: _static/scaling_quality_linear.png

       Linear

    .. figure:: _static/scaling_quality_smooth.png

       Smooth Nearest Neighbour

  * **Pause game when Steam overlay is open**

    Requires a hardware renderer. Enables the game to be paused when using the Steam overlay.

* **Uncap FPS**

  When disabled, the framerate is capped at 40. When enabled, allows the framerate to run higher by generating in-between frames for smoother gameplay.

* **Show FPS**

  When enabled, shows a small number at the top of the screen of the current framerate.

* **Use vertical sync**

  When enabled, attempts to synchronize frames with the monitor's refresh rate, preventing screen tearing.

* **Multithreading**

  Experimental option which, when enabled, uses multiple threads to render.

* **Minimise fullscreen on focus loss**

  When enabled, if the mouse cursor leaves the window in fullscreen mode, minimize the game to the taskbar.


Rendering
---------

* **Landscape Smoothing**

  Enables/disables landscape smoothing on grid edges.

  .. image:: _static/landscape_smoothing.gif

* **Gridlines on Landscape**

  Enables/disables gridlines on the landscape.

  .. image:: _static/landscape_gridlines.png

* **Display text on banners in uppercase**

  If enabled, displays the text on banners (ride entrances, signs) in uppercase.

  .. figure:: _static/banner_text_uppercase.png
     :scale: 200 %

     Uppercase text

  .. figure:: _static/banner_text_lowercase.png
     :scale: 200 %

     Upper and lowercase text

* **Show guest purchases as animation**

  If enabled, shows when guests make a purchase as floating green text.

  .. image:: _static/show_guest_purchases.png

* **Transparent background for giant screenshots**

  If enabled, giant screenshots will have a transparent background where the outside of the park would normally be, instead of the dark void.

* **Virtual floor style**

  Can be one of three values:

  * *Disabled* - No virtual floor is shown when building scenery off ground level.
  * *Clear (Transparent)* - An outline of the current building grid is shown beneath the scenery object being placed.
  * *Glassy (Translucent)* - An outline of the current building grid is shown beneath the scenery object being placed, and the interior of the grid is a translucent olor.

  .. image:: _static/virtual_floor_disabled.png
     :scale: 70 %

  .. image:: _static/virtual_floor_clear.png
     :scale: 70 %

  .. image:: _static/virtual_floor_glassy.png
     :scale: 70 %

* **Cycle day / night**

  If enabled, the game will cycle between day and night cycles, causing the colour palette to change.

  .. image:: _static/day_night_cycle.gif

  * **Enable lighting effects**

    If enabled, light-producing items such as lamps will emit a glow during nighttime and rainstorms.

    * **Enable lighting effects on rides**

      If enabled, some rides will emit a glow during nighttime and rainstorms

* **Render weather effects**

  If enabled, rain and gloomy colours will be rendered during storms

  * **Disable lightning effect**

    If enabled, the lightning effect during thunderstorms will not occur

Culture and Units
-----------------

* **Language**

  Used to select the language OpenRCT2 uses.

* **Currency**

  Used to select the currency OpenRCT2 uses.

  Selecting "Custom currency" will bring up a menu allowing you to specify a currency not built into OpenRCT2.

  .. image:: _static/custom_currency.png

* **Distance and Speed**

  Used to select the units for distances and speed. Can be one of three values:

  * *Imperial* - ``ft`` (feet) and ``mph`` (miles per hour)
  * *Metric* - ``m`` (metres) and ``km/h`` (kilometres per hour)
  * *SI* - ``m`` (metres) and ``m/s`` (metres per second)

* **Temperature**

  Used to select the units for temperature. Can be either ``Celsius`` or ``Fahrenheit``

* **Height Labels**

  Used to select whether to show unit values (``+1``, ``-4``, etc.) or real values (``1.5m``, ``-6m``, etc.)

  .. image:: _static/height_units.png

  .. image:: _static/height_real_values.png

* **Date Format**

  Used to select the date format. Can be one of four values:

  * *Day/Month/Year*
  * *Month/Day/Year*
  * *Year/Month/Day*
  * *Year/Day/Month*

Audio
-----

* **Audio Device Dropdown**

  The first dropdown on the Audio tab is a selector for the audio device that OpenRCT2 will use.

* **Master volume**

  A slider used to adjust the volume of OpenRCT2.

* **Sound effects**

  A slider used to adjust the volume of sound effects such as opening/closing menus, guest chatter, guest purchases, etc.

* **Ride music**

  A slider used to adjust the volume of ride music.

* **Disable audio on focus loss**

  Enables/disables muting of audio when OpenRCT2 is not the focused window.

* **Title screen music**

  Selects the music that will be used at the main menu for OpenRCT2. Can be one of four values:

  * *None*
  * *RollerCoaster Tycoon 1* - requires RCT1 data to work.
  * *RollerCoaster Tycoon 2* - requires RCT2 data to work.
  * *Random title music* - randomly select any of the options above.
