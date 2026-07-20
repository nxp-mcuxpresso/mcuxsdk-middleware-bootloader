# Manufacturing process

This section shows how to execute the MfgTool for the MCU device manufacturing. The key to the MCU bootloader manufacturing with the MfgTool is to have the *ucl2.xml* file completed with all needed commands that are necessary to successfully program the device in a sequence.

The typical setup during manufacturing is shown in the image below with four devices connected to four USB ports to the PC running the MfgTool application.

**Typical setup at manufacturing**


The manufacturing process begins when the operator launches the MfgTool application and clicks the *Start* button.

The MfgTool provides the UI to show the device update progress for each device connected to the PC. The UI also shows the description text that appears in the *ucl2.xml* file for the command that is in execution. To indicate the end of programming for a device, a dummy command can be placed at the end of the *ucl2.xml* file with the text “Done” to conveniently identify the completion of the update so that you know when to switch to the new blank device. The example dummy command to indicate the completion of the update looks like this:

```
<CMD state="Blhost" type="blhost" body="Update Complete!">Done</CMD>
```

The MfgTool is in a continuous update mode until it is stopped by the user by pressing the "Stop" button. No user interaction is necessary on the UI when the "Start" button is pressed, except for pulling off the manufactured device when complete and connecting to the new blank device.



**Parent topic:**[Firmware update process](../topics/firmware_update_process.md)

