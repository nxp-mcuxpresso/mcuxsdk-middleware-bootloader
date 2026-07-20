# MCU bootloader device identification

The MCU bootloader performs the active peripheral detection at device startup to connect to the host to carry out the firmware download operations. If the bootloader device is connected to the UART or the USB, the PC host operating system enumerates the device, either in the USB CDC mode \(via the SDA port, subject to hardware support\), or the USB-HID mode \(not all MCUs have the USB support\). The MfgTool can identify the device’s presence by comparing the active USB devices’ vendor and product identifiers \(VID and PID\) with the supported identifiers mentioned in the &lt;CFG&gt; tag of the *ucl2.xml* file. The MfgTool can connect and update up to four devices simultaneously. The tool supports devices connected to the USB ports either in the HID or CDC modes only. The tool does not support devices connected to the PC via non-USB ports, such as the RS232 ports.

The example of the CFG tag section in the *ucl2.xml* file contains all the possible identification parameters known at the time of the release of this version of the document:

```
<CFG>
    <STATE name="Blhost" dev="KBL-CDC" vid="1366" pid="1015"/>   <!--JLINK CDC-->
    <STATE name="Blhost" dev="KBL-CDC" vid="0d28" pid="0204"/>   <!--mBed CDC-->
    <STATE name="Blhost" dev="KBL-CDC" vid="1357" pid="0707"/>   <!--OpenSDK CDC-->
    <STATE name="Blhost" dev="KBL-CDC" vid="1357" pid="0089"/>   <!--OpenSDA CDC-->
    <STATE name="Blhost" dev="KBL-CDC" vid="1a86" pid="7523"/>   <!--CH340 CDC-->
    <STATE name="Blhost" dev="KBL-CDC" vid="067b" pid="2303"/>   <!--PL2303 CDC-->
    <STATE name="Blhost" dev="KBL-HID" vid="15A2" pid="0073"/>   <!--KBL USB-HID-->
</CFG>
```

The example lists all the possible parameters to save you the time to find them. In an actual use case, you should comment the configuration lines that they do not want to use the corresponding ports for manufacturing. All configuration lines in the CFG tag section are of the same priority. If the number of devices connected to the host is bigger than the number of panels you configured, only the first-enumerated devices are displayed in the panels and the left ones are ignored.

The below figure shows the Windows OS Device Manager showing one MCU bootloader device connected in the USB-HID mode and two devices connected in the USB CDC mode, accessible via serial COM ports 3 and 6.

**Windows OS Device Manager showing MCUs connected in the USB-HID and UART modes**


The figure below shows the corresponding 4-panel MfgTool user interface for the above-connected devices showing one device connected in the HID mode, two devices connected in the CDC mode, and the last panel displaying as "No device connected".

**4-panel UI with three devices connected**


**Note:** See the*MCU Bootloader Demo Applications User's Guide* \(document ID MBOOTDEMOUG\) available at [www.nxp.com/MCUBOOT](http://www.nxp.com/KBOOT) page for instructions on how to connect the target platform MCU.

**Parent topic:**[Firmware update process](../topics/firmware_update_process.md)

