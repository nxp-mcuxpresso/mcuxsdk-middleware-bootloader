# Program Unsigned Image to Flash using MfgTool

Use the following steps to program a boot image into a flash device

1.  Copy the boot\_image.sb file to “&lt;mfgtool\_root\_dir&gt;/Profiles/MRT117x/OS Firmware” folder.
2.  Change the “name” under “\[List\]” to selected option in cfg.ini file in &lt;mfgtool\_root\_dir&gt; folder, for example, “*name = MXRT117x-DevBootFlexSpi1\_FlashXiP*".
3.  Put the RT1170-EVK board to Serial Downloader mode by setting SW1 to “1-OFF, 2-OFF, 3-OFF, 4-ON”.
4.  Power up RT1170-EVK board and insert USB cable to J20.
5.  Open MfgTool, it will show as the detected device like the one shown in [Figure 1](#rt1170_FIG_KZT_HJ1_5GB).
6.  Click “Start”, MfgTool will do manufacturing process. After completion, it will show the status as success as shown in Figure 16. Click “Stop” and close the MfgTool.
7.  Put the RT1170-EVK board to internal boot mode and select QSPI FLASH as boot device by setting SW1 to “1-OFF, 2-OFF,3-ON, 4-OFF”. Then reset the device to start running the application

**Parent topic:**[Example of manufacturing flow for RT1170-EVK](../topics/example_of_manufacturing_flow_for_rt1060_rt1064_rt.md)

