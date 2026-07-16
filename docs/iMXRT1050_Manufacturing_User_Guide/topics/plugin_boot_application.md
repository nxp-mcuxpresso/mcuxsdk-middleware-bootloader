# Plugin boot application 

The plugin boot application is usually used to enable boot features that are not natively supported by Boot ROM, for example,

-   Boot from USB disk
-   Boot from Ethernet
-   DDR/SDRAM configuration
-   Redundant boot/reliable boot

The prototype of plugin boot application is:

boot (\*plugin\_download\)(void \*\*start, size\_t \*bytes, uint32\_t \*ivt\_offset\);

```{include} principles_for_plugin_boot_application_design.md
:heading-offset: 2
```

```{include} boot_flow_of_plugin_boot_application.md
:heading-offset: 2
```

```{include} example_plugin_boot_application_to_enable_non-xip_.md
:heading-offset: 2
```

```{include} images_loaded_by_plugin_boot_application.md
:heading-offset: 2
```


