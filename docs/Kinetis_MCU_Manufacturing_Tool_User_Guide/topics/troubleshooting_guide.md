# Troubleshooting guide

The MfgTool logs the command and response from the device into the *MfgTool.log* file. When the device returns a failure code for a command or times out or for any other reason, the MfgTool UI indicates the occurrence of the failure. The cause can be diagnosed by inspecting the *MfgTool.log* file. To open the *MfgTool.log* file, it is recommended to stop the MfgTool using the "Stop" button, because the MfgTool continuously logs information to the file.

Example:

In this example, the “*Get Property 1*” command was sent to two devices. One device failed and one succeeded. Here is the corresponding MfgTool UI:

**UI showing successful update for the first device and error for the second device**


The red progress bar indicates that the device connected to the Hub 4-Port 1 failed. The corresponding result, logged to the *MfgTool.log* file looks as follows:

```
ModuleID[2] LevelID[10]: CmdOperation[0] device changed and reset to state 0
ModuleID[2] LevelID[10]: ExecuteCommand--Blhost[WndIndex:0], Body is get-property 1
ModuleID[2] LevelID[10]: CmdOperation[1] device changed and reset to state 0
ModuleID[2] LevelID[10]: ExecuteCommand--Blhost[WndIndex:1], Body is get-property 1
ModuleID[2] LevelID[10]: Get Property 1  [WndIndex:0] {
   "command" : "get-property",
   "response" : [ 1258357504 ],
   "status" : {
      "description" : "0 (0x0) Success.",
      "value" : 0
   }
}
ModuleID[2] LevelID[10]: Get Property 1  [WndIndex:1] {
   "command" : "ping",
   "response" : [],
   "status" : {
      "description" : "10500 (0x2904) No response received for ping command.",
      "value" : 10500
   }
}
```

The “**WndIndex**” shows the device index on the MfgTool UI for which the results are logged. The first two lines indicate the get-property 1 sent to two devices with WndIndex 0 and 1.

The next lines are the capture of the blhost output on the stdout. The blhost output suggests that one device did not respond to the ping sent by the blhost and returned error code 10500. The other device returned success code \(0\) for the Get Property 1 command and the response text shows the exact value returned by the device for the Get Property 1 command.


```{include} ../topics/examples_of_common_failure_error_messages_in_the_l.md
:heading-offset: 1
```

