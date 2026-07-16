# Generate SB file for bootable image programming

To make the manufacturing process easier, all the commands supported by the flashloader and bootable image can be wrapped into a single SB file. Even if there are any changes in the application, MfgTool still uses this SB file to manufacture. The SB file can be updated separately without updating scripts for MfgTool use.

In this chapter, a bootable image will be created using the method in former chapter. Then corresponding SB file is generated using the bootable image. The BD file is prepared first to generate SB file for bootable image.


```{include} generate_sb_file_for_flexspi_nor_image_programming.md
:heading-offset: 1
```

```{include} generate_sb_file_for_flexspi_nand_image_programmin.md
:heading-offset: 1
```

```{include} generate_sb_file_for_sd_image_programming.md
:heading-offset: 1
```

```{include} generate_sb_file_for_emmc_image_programming.md
:heading-offset: 1
```

```{include} generate_sb_file_for_serial_nor_eeprom_image_progr.md
:heading-offset: 1
```

```{include} generate_sb_file_for_semc_nor_image_programming.md
:heading-offset: 1
``` 

```{include} generate_sb_file_for_semc_nand_image_programming.md
:heading-offset: 1
``` 

```{include} generate_sb_file_for_fuse_programming.md
:heading-offset: 1
```

