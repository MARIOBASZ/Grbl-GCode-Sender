## ioSender changelog

2024-12-30: [Release 2.0.45](https://github.com/terjeio/Grbl-GCode-Sender/releases/tag/2.0.45).

* Added spindle selection using drop down, ref. issue #399.
* Remove R\(eset\) Signals "LED" if the input is not available.
* Fixes for issue #414 & #420, heightmap probing failures. NOTE: these issues were due to a regression in a 2.0.45 prerelease.
* Added parser support for block delete character.
* Added filter button in SD card viewer for show/hide non-CNC files.
* Allow use of modified legacy Grbl controller.
* Added support for spindle selection when multiple spindles is available.
* No longer stops jobtimer when changing tool.
* Added FTP port settings, available when controller supports FTP file transfer.
* Fixed and improved lathe turning wizard, taper mode.
* Improved handling of cycle start signal
* Improved tool length probing
* Added pre/post probing job macro support.
* Added Edge offset input in Edge finder tabs.
* A number of minor bug fixes and improvements.

2023-12-30: [Release 2.0.44](https://github.com/terjeio/Grbl-GCode-Sender/releases/tag/2.0.44).

* Fix for issue #350 - improved handling of cycle start message coming from the controller to avoid unwanted start of loaded program.
* Fix for issue #350 - Z probe with unexpected result in Probing tab.
* Fix for issue #339- removed unpublished files from builds.
* Fix for issue #310 - run time not updaing when streaming from SD card.
* Added right click menu in the program listing to start from a given block, execute a single block or send selected commands to the controller.
* Added Plasma THC flyout to sidebar menu. Visible when the controller supports THC. Plus fix for issue #331.
* Updated rendering of canned cycles to match latest grblHAL controller release.
* Added support for UVW lathe mode.
* Added handling of controller auto-reporting mode, will be disabled when the sender is connected.
* A number of minor bug fixes and improvements.

2023-07-30: [Release 2.0.43](https://github.com/terjeio/Grbl-GCode-Sender/releases/tag/2.0.43).

* Added gcode parser support for flow control statements. Note that this does not yet include validation.
* Added ".macro" as selectable filetype for SD card upload.
* Fix for issue #289 - crash when open some GRBL settings.
* Fix for issue #290 - cannot read settings on startup after exiting door mode, fix for lathe mode axis settings handling.
* Fix for issue #307 - camera offset applied multiple times after closing/reopening camera view.
* Fix for issue #309 - illegal value \(NaN\) returned when DRO field is blank.
* Fix for issue #310 - SD Card, Download and Run, no Program tab or Run time update.
* Added handling of new grblHAL auto reporting feature and support for some $-commands, such as settings, while critical events are active. Fixes issue #298.
* Rotation: added option to determine X0,Y0 for right angled workpiece.
* 3D viewer: improved grid handling, disabled show work envelope button if homing is not enabled/done.
* Added facing wizard for lathes, issue #287.

2023-03-22: [Release 2.0.42](https://github.com/terjeio/Grbl-GCode-Sender/releases/tag/2.0.42).

* Fix for incorrect handling of coordinates when controller is in inches mode (setting $13). Issue #283.  
__NOTE:__ Probing and gcode conversions/transforms are performed in metric (G21 active), probing with controller is in inches mode has only been lightly tested.
* Workaround for _MPos_ flyout not showing coordinates when number of axes > 3 plus fix for heightmap probing issues. Issue #279.
* Cannot zero _DRO_ in probing tab, causes exception. Issue #273.
* Fix for lathe mode _DRO_ display. Issue #270.
* Fix for missing color selectors for 3D viewer in app setup. Issue #263.
* Fix for inaccurate tool length offset calulated \(_Tool length offset_ tab\). Issue #262.
* Fix for issue with heightmap transform corrupting arcs. Issue #261.
* Added _View all_ submenu to SD card filelist popup menu, for getting an unfiltered list. Requires grblHAL controller with support for the _$F+_ command.
* Improved handling for some grblHAL setting types.
* Added Hungarian translation, thanks to @dobakszilard \(issue #267\).
* Some minor changes and improvements.

---

2022-11-17: [Release 2.0.41](https://github.com/terjeio/Grbl-GCode-Sender/releases/tag/2.0.41).

* Fix for incorrect handling of negative values entered in DRO. Issue #240.
* Fix for incorrect handling of odd com port names \(with leading spaces\). Issue #230.
* Now sets Real Time Clock \(RTC\) on connect to controllers that has a RTC.
* Added support for up to 9 axes \(XYZABCUVW\) and remapping of ABC to UVW. Part of fix for [iMXRT1062 issue #43](https://github.com/grblHAL/iMXRT1062/issues/43).
* Fixed bug that caused multi-pass center finder probing to sometimes fail.
* Added baud rate selection to connection dialog.
* Added support for LightBurn clusters \(when enabled in the controller\).
* Added option for verifying probe connection before commencing a probe sequence.
* Added _Measure_ option to some probing tabs, this logs probed coordinate to the console for now. Further functionality planned.
* Added DRO view to Probing tab. Persistent in XL version, dependent on main window width in standard version.

---

2022-07-18: [Release 2.0.40](https://github.com/terjeio/Grbl-GCode-Sender/releases/tag/2.0.40).

* Fix for incorrect rendering of paths consisting of many small moves. Issue #235
* Fixed spindle RPM entry not working when spindle is running. Issue #236
* Added retries on startup if unexpected data received from controller.
* Added parser/rendering support for G5.1 splines and [multi turn G2/G3 arcs](http://linuxcnc.org/docs/html/gcode/g-code.html#gcode:g2-g3) controlled by P word.
Requires grblHAL controller with support for those commands \(not yet released\).

---

2022-07-05: [Release 2.0.39](https://github.com/terjeio/Grbl-GCode-Sender/releases/tag/2.0.39).

* Fixed MPG mode switching issue, "hardened" code.
* Removed dependency on XCeed WPF toolkit. WPF toolkit issue [#1598}(https://github.com/xceedsoftware/wpftoolkit/issues/1598) and sender issue [#231](https://github.com/terjeio/ioSender/issues/231).
* UI color selection for 3D viewer disabled. Color changes has to be done by editing _App.config_ until a new color picker is found or made.

---

Executable for development builds available for download [here](http://www.io-engineering.com/downloads/) if you want to participate in testing.

2022-06-12: [Release 2.0.38](https://github.com/terjeio/Grbl-GCode-Sender/releases/tag/2.0.38).

* Added paste support for numeric input fields.
* Improved rotation support.
* Fixed bounding box calulation for arcs.
* Improved number of axes detection and handling. Now supports > 3 axis lathe configurations.
* General "hardening" of code.
* Translation updates.

---

2022-03-11: [Release 2.0.37](https://github.com/terjeio/Grbl-GCode-Sender/releases/tag/2.0.37).

* Added list of controller alarm and error codes to _Help_ menu.
* Added link to tutorial videos to  _Help_ menu. By @S2000Stefan
* Added link to guided tour blog post to  _Help_ menu. By @phil-barrett
* Improved camera handling, can now be used for center probing. New camera settings options added to _App: Settings_ tab.
* Fixed bugs in height map probing causing intermittent application hang.
* Added mapping of G-code to rotary axis to _File > Transform_ menu. Experimental.
* Modified _Grbl_ tab layout in XL version to always show _Outline_ box.
* Added support for custom keyboard shorcut mappings, current mappings can be exported from the _App: Settings_ tab.
* General "hardening" of code.

---

2022-01-27: [Release 2.0.35](https://github.com/terjeio/Grbl-GCode-Sender/releases/tag/2.0.36).

* Fixed nasty bug where crazy motions could happen if a probing sequence was stopped before completion.
* Improved support for legacy Grbl controllers.
* Added keyboard jogging for A-axis when enabled. 
* Added keyboard jogging commands that uses settings from the UI jog panel for speed and distance. Intended for joypad use.
* Added buttons for controlling 3D-view modes and for saving/restoring current view.

---

2021-21-26: Release candidate for build 36, changelog will be added later.

---

2021-10-26: [Release 2.0.35](https://github.com/terjeio/Grbl-GCode-Sender/releases/tag/2.0.35).

* Added support for localization \(translation\) see the [Wiki](https://github.com/terjeio/ioSender/wiki/Localization) for details.
* Added `-locale` startup parameter for overriding the default language read from the OS.
* Added sender configuration for not checking probe state before probing @G59.3, if probe is asserted it will result in alarm that has to be cleared.
* Added signals box to Trinamic tuner.
* Changed keyboard jogging to always use metric mode.
* Limit keyboard jog commands to be within machine limits if not handled by the controller.  
__NOTES:__ Machine has to be homed for this to work properly, N_KEY rollower is not supported neither is fast tapping of keys.  
grblHAL users should set `$40` to `1` for the best keyboard jogging functionality.
* Added description to com ports selection drop-down.
* Improved program limits calculation.
* Some minor bug fixes.

---

2021-08-20: [Release 2.0.34](https://github.com/terjeio/Grbl-GCode-Sender/releases/tag/2.0.34).

Sender:

* Added optional text overlay to 3D-viewer.
* Improved controller settings handling, with grblHAL controller build >= 20210819 up to date descriptions are fetched from the controller and unsupported checkboxes are hidden.
* Added app settings for jog flyout, for distances and speeds.
* Added checkbox for on-the-fly \(while job is running\) control of fan. Requires grblHAL controller with optional fan plugin installed.
* Bug fixes, some pretty obscure.

Config app:

* Updated for latest libraries.
* Added fetch and save of settings information for sender use in Grbl- and grblHAL-format. Requires grblHAL controller build 20210819 or later.

---

2021-05-16: [Release 2.0.33](https://github.com/terjeio/Grbl-GCode-Sender/releases/tag/2.0.33).

* Added _Rotation_ tab to _Probing_ and _Rotate_ submenu to _File > Transform_.
* Added experimental _Compress_ submenu to _File > Transform_.  
This removes superfluous G-code commands and values from the loaded program.
* Added color selection for elements in the 3D-viewer in the _Settings: App_ tab.
* Increased the size of some UI buttons for easier use from touch screens.
* Increased the minimum window size somewhat, some minor UI layout changes related to that.
* Added tab for network connection parameters to connection dialog.
* Bug fixes, mainly for the tokenizer/detokenizer.

2021-04-27: [Release 2.0.31](https://github.com/terjeio/Grbl-GCode-Sender/releases/tag/2.0.31).

* Renamed executable to ioSender.exe.
* Improved grbl settings tab: error handling and reload from backup.
* Improved probing tabs: input validation and alarm handling.
* Improved SD Card tab: added experimental YModem based upload and context menu for file actions.  
YModem upload requires grblHAL controller build 20210421 or later.
* Improved jog flyout: when active numeric pad 2 and 8 can be used to change feed rate.
* Bug fixes and code hardening.

---

2020-12-14: [Beta release 8](https://github.com/terjeio/Grbl-GCode-Sender/releases/tag/v028-beta8).

* Added treeview for settings when settings details is available from the controller.
* Added option for single direction probing to center finder \(unlock XY and set the size to 0 for direction not to probe\).
* Added truncate of comment lines on send.
* Some bug fixes.

Since a treeview of controller settings has been added this is still a beta release.

---

2020-09-29: [Beta release 7](https://github.com/terjeio/Grbl-GCode-Sender/releases/tag/v027-beta7).

* Minor changes to message handling on alarm.

This is likely to be the last beta release, no new features will be added before the first production release.

---

2020-09-28: Development build for testing.

* Added gcode preview to center finder.
* Enabled function key shortcuts for macros in probing tab.
* Fixed profile handling in probing tab.
* Added simple probe protect to parts of probing sequence.  
Requires grblHAL based controller with build 20200927 or later and _Run substatus_ enabled in _Status report options_.  
NOTE: "simple" because the sender will cancel non-probing motions and stop the sequence when receiving a probe triggered message.
This message can be delayed up to the status report polling time, typically 200 ms.  
__Warning:__ do _not_ rely on this saving your probe from probing setup mistakes.
* Bug fixes.

---

2020-09-26: Development build for testing.

* Added gcode preview to edge finders, based on code/input from @jschoch
* Added workaround for [legacy grbl](https://github.com/gnea/grbl) in order to keep probing UI in sync with controller status.
* Bug fixes.

---

2020-09-21: Development build for testing.

* Added machine position flyout.
* Added warning about setting tool length reference if job has tool changes.
* Added support for non-uniform heightmap grid size.
* Added floating console window, show/hide it from the _File_ menu.
* Added filter to suppress real time messages in console.
* Bug fixes, a major one was heightmap probing could exceed the defined area to be probed.
* Added home position in machine coordinates to the core viewmodel, will be set by new message. From next build of grblHAL.  
Axes not homed is set to `double.NaN`.

---

2020-09-17: Development build for testing.

* Added TLO \(Tool Length Offset\) and TLO referenced "LEDs" to _Work Parameters_ box in the _Grbl_ tab.  
The first will lit when a tool offset is active, the second when a tool offset reference is set \(grblHAL only\).
* Added app setting for whether the MDI field should keep focus on a tab change.
* Added \<Ctrl\>+\<Shift\> as keyboard shortcut in the MDI to reenable keyboard jogging.  
This as keyboard jogging is disabled when an input field has focus and tabbing may move focus elsewhere.
* Added display of current block number executing (technically last ok'ed block) in status line.
* Refactored probing to use machine position moves as much as possible.
* Added internal edge finder.
* Added option of adding number of passes to run in center finder and XY dimensions input instead of diameter.
* Added option for setting Z offset in _Tool Length Offset_ tab.
* Bug fixes.

---

2020-09-04 : Sixth [beta release](https://github.com/terjeio/Grbl-GCode-Sender/releases/tag/v026-beta6). 

Refactored probing to work with networking protocols. Some bug fixes and new shortcuts added since beta 1.

---

2020-08-05 : First [beta release](https://github.com/terjeio/Grbl-GCode-Sender/releases/tag/v021-beta1). 

Updated for latest \(20200805\) grblHAL [tool change functionality](https://github.com/terjeio/grblHAL/wiki/Manual,-semi-automatic-and-automatic-tool-change), bug fixes for tool change handling \(UI was not correctly enabled for the different state changes\).

---

2020-07-22: Alpha 20 release of binary.

Changes to probing and updates for new features in grblHAL. This release is for testing of new features both in the sender and in grblHAL. Revert to alpha 19 if problems arise.

Active development will not restart until the summer holidays are over.

---

2020-05-20: Alpha 19 release of binary.

Changes:
 * Major refactoring of probing tab:  
  Inspired by probing [plugin for LinuxCNC](https://vers.by/en/blog/useful-articles/probe-screen) \(IMO a good reference\).  
  Allows definition of probing profiles.  
  Shortcut for enabling keyboard jogging: `<CRTL>+<SHIFT>`  
  Tool length probing now honors toolplate/fixture height, new input field for workpiece height.  
  Center finder workpiece diameter defaults to 0.  
  Option to automatically set G92 offset (tool zero) at heightmap origin.  
  Some sanity checks performed on data input.  
  Note: tool length probing is not yet complete, fixture probing and tool table/tool length options remains. 
  USE WITH CARE!
* Sidebar flyouts can be activated with `Alt` shortcuts.  
* Bug fixes.

---

2020-05-09: Alpha 18 release of binary.

Changes:

* `<Ctrl>+<H>` shortcut for homing added.
* Keyboard jogging can be enabled when probing tab is active. Jog flyout always active in probing tab.
* Number of blocks (lines) in loaded program shown in status bar.
* Option for real time display of parser state in grbl tab (requires latest grblHAL build)
* Some semantic changes, e.g. _File > Open_ is now _File > Load_.
* Bug fixes, internal changes.

---

2020-04-17: Alpha 17 release of binary.

Changes:

* Resizable UI.
* Toolbar with file handling tools, display of user defined macros with keyboard shortcuts.
* Status bar for messages, run time and keyboard jog step size \(jogging with \<CTRL\>+cursor keys\).
* Keyboard step jogging made available for non-grblHAL firmware. Change beetwen step sizes on the fly with numeric keypad `4` and `6`. Feed rate is fixed to setting in _Settings: App_ tab. 
* Shortcuts for sidebar flyouts \(use Alt+underscored letter\).
* Cursor key jogging when jog flyout is active, even for non grblHAL firmware. _No_ autorepeat!.
* Change step size and feedrate with keyboard shortcuts when jog flyout is active. Bound to numeric keypad `2`, `4`, `6` and `8`.
* [Manually](https://github.com/terjeio/Grbl-GCode-Sender/wiki/Usage-tips) associate GCode filetypes with sender.

---

2020-04-11: Alpha 15 release of binary.

Added interfaces for GCode conversion \(from other file formats\) and transformation.

Initially I have added two converters that I need for drilling, milling board outlines and making solder paste stencils from [KiCad](https://www.kicad-pcb.org/) PCB designs:

* Excellon to G81 drill commands. Has support for slots (Excellon G85). `.drl` filename extension required. Only for [grblHAL](https://github.com/terjeio/grblHAL) firmware.

* HPGL to edge cuts or solder paste stencil \(when firmware is in laser mode\). `.plt` filename extension required.

Two transformers added \(available from _File>Transform_ menu\):

* Arc to lines. Replaces Arcs \(G2, G3\) and splines \(G5\) with line segments. Arc tolerance from grbl firmware setting.

* Add drag knife moves.

__Note:__ these conversions and transformations has not yet been tested in a machine! Use with care.

Added _File>Save_ menu option for saving converted/transformed GCode.  
__NOTE:__ Only metric output for now. Blocks will be reorganized to comply with NIST ordering. Again, use with care! 

Lathe mode extensions: 3D viewer switched to XZ plane. G33 and G76 rendering implemented.

Added setup option to to enable keyboard jogging when firmware is not grblHAL. [Understand the risks involved](https://github.com/terjeio/Grbl-GCode-Sender/wiki/Known-limitations) before doing so!

Many internal changes - perhaps the most important is a GCode emulator that is used by functions such as 3D rendering and transformations. Some bug fixes.

---

2020-03-29: Alpha 14 release of binary.

Added probing tab with tool length, edge finder, center finder and height map options. __NOTE:__ This has NOT been extensively tested! G20 (inches) mode not tested at all! Do not use unless you understand the risks.

Disabled keyboard jogging when firmware is not grblHAL](https://github.com/terjeio/grblHAL). May add setup option to reenable later.

Many internal changes.

---

2020-03-16: Alpha 13 release of binary.

Program list control has been replaced vith a tab control with easy access to a 3D view and a console (for showing replies from grbl).

Added bounding box calculation for arcs (G2 & G3), _Program limits_ should now be accurate.

---

2020-01-22: First alpha release of binary. Use with care and please report issues!

__NOTE:__ Keyboard jogging with a grbl firmware other than grblHAL is likely to fail, this is a firmware problem so no plan to fix. grblHAL _may_ also occasionally fail \(likely due to issues in the sender\) so be ready to hit reset/estop if it goes wrong!

__NOTE:__ .Net Runtime version 4.5.2 is required, so this sender is for Win7 or later.

Some known issues:

* The 3D-viewer will slow down loading of large files, if this is a problem then disable it in app settings. __Fixed.__

* A restart is required after changing most app settings.

* Lathe mode wizards may generate bad code, needs comprehensive testing. NOTE: As far as I know currently only grblHAL for MSP432 supports G76 for threading, all other builds will generate an error on G76. The G76 code generated is the linuxCNC variant.

* There is no UI yet for configuring streaming via telnet or websocket protocols, either the app config file must be edited or the connection parameter has to be supplied on the command line.

* Program limits displayed does not include arcs correctly if outside the bounding box defined by linear moves. __Fixed.__
