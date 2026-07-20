# Initialization files

This section focuses on the parameters controlling the appearance of the MfgTool User Interface and other behavior that can be controlled via the initialization files with the *.ini* extension. The initialization files can be edited using any text editor.

-   The *UICfg.ini* file is used to configure the number of ports that indicates the number of devices that can be simultaneously attached to multiple USB ports of the host PC and programmed simultaneously. The MfgTool presents one panel for each port on its GUI.

The format of the *UICfg.ini* file is as follows:

```
[UICfg]
PortMgrDlg=1
```

For example, if only one device is supported at a time, the "PortMgrDlg=1" should be set. The UI display with one dialog or panel is shown in this figure:

**MfgTool UI with one panel in UICfg.ini**


A maximum of up to four devices that can be simultaneously connected and updated using the MfgTool is supported. The PortMgrDlg entry in the *UICfg.ini* file can be set to any of one, two, three, or four panels, depending on the manufacturing needs. Here is an example screenshot with four ports:

**MfgTool UI with four panels in UICfg.ini**


-   The *cfg.ini* file is used to configure the target chip profile and target operation list.

The format of this file is as follows:

```
[profiles]
chip = Kinetis Bootloader
[platform]
board =
[LIST]
name = Kinetis-bootloader
```

The “profiles/chip” entry indicates the target profile name which should match the target folder name at "profiles/", and the “list/name” entry indicates the target operation list name which should match the LIST tag entry in the *ucl2.xml* file located at "profiles/Kinetis Bootloader/OS Firmware/". The “platform/board” entry is reserved and not used.

