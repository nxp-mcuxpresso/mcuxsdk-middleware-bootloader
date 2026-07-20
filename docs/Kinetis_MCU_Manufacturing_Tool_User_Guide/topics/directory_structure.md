# Directory structure

The MfgTool for MCU devices is bundled together with the MCU bootloader in `<sdk_package>/middleware/mcu-boot`. The following figure provides the mfgtools-rel directory structure on the host PC after the package installation.

**MCU bootloader folder hierarchy**


In the package, the *mfgtools-rel* folder appears in the *middleware/mcu-boot/bin/tools*. *blhost*is released on MCUBOOT webpage [nxp.com/MCUBOOT](http://www.nxp.com/MCUBOOT).

The blhost.exe file appears in the *bin/Tools/blhost/win* folder and the MfgTool executable *MfgTool2.exe* appears in the *mfgtools-rel*folder.

The *Profiles* folder contains the profile for the MCU bootloader device that includes the *OS Firmware* folder and the *player.ini*file.

The *files* folder in the *OS Firmware* folder may include the application image along with the custom files to download onto the device.

The *ucl2.xml* file in the *OS Firmware* folder is the main XML that the MfgTool processes. It contains the flow of the manufacturing process for the device, which includes the identification parameters for the device and the blhost commands sequenced to query the device and program the image. The example *ucl2.xml* file is delivered with the USB device identification parameters to identify the MCU bootloader device connected to the PC host and the set of blhost commands required for updating the image on the device. The *ucl2.xml* file can be customized to suit the custom setup or the manufacturing process flow. The folder contains several example xml files for your reference.

The *player.ini* file in the 'Kinetis Bootloader' profile folder contains configurable parameters for the manufacturing tool application.

The *cfg.ini* and *UICfg.ini* files provide the customizable parameters for the look and feel of the tool’s GUI.

The *MfgTool.log* text file is a useful tool to debug the failures reported in the MfgTool UI. The MfgTool logs the entire command line string it used to invoke the blhost, and also collects the output response text that the blhost puts out on stdout into the *MfgTool.log* file. The log file is the first place to look into when troubleshooting. The troubleshooting guide section at the end of this document discusses more on the information the tool logs into the *MfgTool.log* text file.

