# Device panel

The device panel shows the PC hub and port numbers at the top of the pane to which the MCU bootloader device is connected.

The UI element “Drive\(s\)” is not applicable for MCU bootloader devices.

The next UI element shows the type of device connected in the idle state. The MCU bootloader device is connected in the USB-HID mode and the display shows ‘HID-compliant device’. When connected in the UART mode, the text shows the respective virtual COM port number along with the description of the device \(as it appears in the Windows® OS device manager\). While manufacturing \(non-idle state\), the same element shows the command in the execution. When MfgTool is complete, the command sequences succesfully. The element can be made to display text such as ‘Done’, which is discussed later on in this document. When the manufacturing process is halted by the user using the "Stop" button, the text reverts back to the device description. The example screenshot below shows four MCUs connected to four USB ports in the HID and CDC modes in the idle state.

**UI showing four MCUs connected to the PC host in the idle state**


The last two UI elements of the device pane are the progress bars that show the progress while manufacturing. The first element shows the progress of the current blhost command being executed, and the second element shows the overall progress to complete the execution of all the commands listed in the ucl2.xml file. The progress bar appears in three different colors. Blue color indicates that the manufacturing is in process, green color indicates that the manufacturing completed successfully, and red color indicates that an error occurred. The error information are logged into the Mfgtool.log file for decoding purposes.

**Parent topic:**[GUI elements](../topics/gui_elements.md#)

