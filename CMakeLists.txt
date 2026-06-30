
if(CONFIG_MCUX_PRJSEG_kboot_common_settings)
    mcux_add_configuration(
        AS  "-DDEBUG -DNDEBUG"
        CC  "-DDEBUG -DNDEBUG"
        CX  "-DDEBUG -DNDEBUG"
    )
endif()

if(CONFIG_MCUX_PRJSEG_imx_kboot_common_settings)
    mcux_add_iar_configuration(
        AS  ""
        CC  "--diag_suppress Pa082,Pe177,Pe186,Ms014,Pa182"
        CX  "--diag_suppress Pa082,Pe177,Pe186,Ms014,Pa182"
    )
    mcux_add_mdk_configuration(
        CC  "-fshort-enums -fshort-wchar -ffunction-sections -fno-common -fdata-sections -ffreestanding -fno-builtin -mthumb -fno-rtti -Wno-null-dereference -Wno-unknown-attributes -Wno-expansion-to-defined -Wparentheses-equality -Wno-invalid-noreturn -g -Oz"
        CX  "-b -fno-common -ffunction-sections -Wunused-command-line-argument -fdata-sections -ffreestanding -fno-builtin -mthumb -fno-rtti -fno-exceptions -g -Oz"
        LD "--library_type=microlib"
    )
    mcux_add_armgcc_configuration(
        AS  "-mthumb -D__STARTUP_CLEAR_BSS"
        #-Wno-unused-variable -Wno-unused-function -Wno-maybe-uninitialized -Wno-missing-braces is used to fix the warning, for example: "Y" defined but unused "S" may be used uninitialized "B" missing braces around initializer
        CC  "-fno-common -ffunction-sections -fdata-sections -ffreestanding -fno-builtin -mthumb -mapcs -std=gnu99 -g -O0 -Os -Wno-unused-variable -Wno-unused-function -Wno-maybe-uninitialized -Wno-missing-braces"
        CX  "-fno-common -ffunction-sections -fdata-sections -ffreestanding -fno-builtin -mthumb -mapcs -fno-rtti -fno-exceptions -g -O0 -Os"
    )
endif()

if(CONFIG_MCUX_PRJSEG_kinetis_kboot_common_settings)
    mcux_add_iar_configuration(
        AS  ""
        CC  "--diag_suppress Pa039,Pe068,Pe069,Pa082,Pe177,Pe186,Pe550,Pa050,Pe1105,Pe1305,Pa182 --no_unroll -e --use_c++_inline --silent --debug"
        CX  "--diag_suppress Pa039,Pe068,Pe069,Pa082,Pe177,Pe186,Pe550,Pa050,Pe1105,Pe1305,Pa182 -e --silent --debug"
    )
    mcux_add_mdk_configuration(
        CC  "-std=c99 -fshort-enums -fshort-wchar -ffunction-sections -fno-common -fdata-sections -ffreestanding -fno-builtin -mthumb -fno-rtti -Wno-unused-command-line-argument -Wno-null-dereference -Wno-unknown-attributes -Wno-expansion-to-defined -Wno-invalid-noreturn -g -Oz"
        CX  "-fno-common -ffunction-sections -fdata-sections -ffreestanding -fno-builtin -mthumb -fno-rtti -fno-exceptions -g -Oz"
        LD "--library_type=microlib"
    )
    mcux_add_armgcc_configuration(
        AS  "-mthumb -D__STARTUP_CLEAR_BSS"
        CC  "-fno-common -ffunction-sections -fdata-sections -ffreestanding -fno-builtin -mthumb -mapcs -std=gnu99 -g -Os -Wno-unused-variable"
        CX  "-fno-common -ffunction-sections -fdata-sections -ffreestanding -fno-builtin -mthumb -mapcs -fno-rtti -fno-exceptions -g -Os"
    )
endif()

if(CONFIG_MCUX_PRJSEG_lpc_kboot_common_settings)
    mcux_add_iar_configuration(
        AS  ""
        CC  "--diag_suppress Pa082,Pe177,Pe550,Pe188,Pa182"
        CX  "--diag_suppress Pa082,Pe177,Pe550,Pe188,Pa182"
    )
    mcux_add_mdk_configuration(
        CC  "-fshort-enums -fshort-wchar -ffunction-sections -fno-common -fdata-sections -ffreestanding -fno-builtin -mthumb -fno-rtti -Wno-null-dereference -Wno-unknown-attributes -Wno-expansion-to-defined -Wno-invalid-noreturn -g -Oz"
        CX  "-b -fno-common -ffunction-sections -fdata-sections -ffreestanding -fno-builtin -mthumb -fno-rtti -fno-exceptions -g -Oz"
        LD "--library_type=microlib"
    )
    mcux_add_armgcc_configuration(
        AS  "-mthumb -D__STARTUP_CLEAR_BSS"
        CC  "-fno-common -ffunction-sections -fdata-sections -ffreestanding -fno-builtin -mthumb -mapcs -std=gnu99 -g -O0 -Os -Wno-unused-variable -Wno-unused-function -Wno-maybe-uninitialized -Wno-missing-braces -Wno-strict-aliasing"
        CX  "-fno-common -ffunction-sections -fdata-sections -ffreestanding -fno-builtin -mthumb -mapcs -fno-rtti -fno-exceptions -g -O0 -Os"
    )
endif()

if(CONFIG_MCUX_PRJSEG_evkbimxrt1050_kboot_options)
    mcux_add_iar_configuration(
        AS  ""
        CC  "-DCPU_MIMXRT1052DVL6B -DCPU_IS_ARM_CORTEX_M7=1"
        CX  ""
    )
    mcux_add_mdk_configuration(
        AS  "-mcpu=cortex-m7"
        CC  "-mcpu=cortex-m7 -DCPU_MIMXRT1052DVL6B -DCPU_IS_ARM_CORTEX_M7=1"
        CX  "-mcpu=cortex-m7"
    )
    mcux_add_armgcc_configuration(
        AS  "-mcpu=cortex-m7 -mfloat-abi=hard -mfpu=fpv5-d16 -mthumb"
        CC  "-mcpu=cortex-m7 -mfloat-abi=hard -mfpu=fpv5-d16 -mthumb -MMD -MP -DCPU_MIMXRT1052DVL6B -DCPU_IS_ARM_CORTEX_M7=1"
        CX  "-mcpu=cortex-m7 -mfloat-abi=hard -mfpu=fpv5-d16 -mthumb -MMD -MP"
    )
endif()

if(CONFIG_MCUX_PRJSEG_evkbmimxrt1060_kboot_options)
    mcux_add_iar_configuration(
        AS  ""
        CC  "-Ohz -DCPU_MIMXRT1062DVL6B -DCPU_IS_ARM_CORTEX_M7=1 -DXIP_EXTERNAL_FLASH=1 -DNDEBUG"
        CX  "-DNDEBUG"
    )
    mcux_add_mdk_configuration(
        AS  "-mcpu=cortex-m7 -DNDEBUG"
        CC  "-mcpu=cortex-m7 -Oz -DCPU_MIMXRT1062DVL6B -DCPU_IS_ARM_CORTEX_M7=1 -DXIP_EXTERNAL_FLASH=1 -DNDEBUG"
        CX  "-mcpu=cortex-m7 -Oz -DNDEBUG"
    )
    mcux_add_armgcc_configuration(
        AS  "-mthumb -D__STARTUP_CLEAR_BSS -DNDEBUG"
        CC  "-mthumb -MMD -MP -Os -DCPU_MIMXRT1062DVL6B -DCPU_IS_ARM_CORTEX_M7=1 -DNDEBUG"
        CX  "-mthumb -MMD -MP -Os -DNDEBUG"
    )
endif()

if(CONFIG_MCUX_PRJSEG_evkbmimxrt1170_cm7_kboot_options)
    mcux_add_iar_configuration(
        AS  "-DNDEBUG"
        CC  "-Ohz -DCPU_MIMXRT1176DVMAB_cm7 -DCPU_IS_ARM_CORTEX_M7=1 -DXIP_EXTERNAL_FLASH=1 -DXIP_BOOT_HEADER_ENABLE=1 -DNDEBUG"
        CX  "-DNDEBUG"
    )
    mcux_add_mdk_configuration(
        AS  "-mcpu=cortex-m7 -DNDEBUG"
        CC  "-mcpu=cortex-m7 -Oz -DCPU_MIMXRT1176DVMAB_cm7 -DCPU_IS_ARM_CORTEX_M7=1 -DXIP_EXTERNAL_FLASH=1 -DXIP_BOOT_HEADER_ENABLE=1 -DNDEBUG"
        CX  "-mcpu=cortex-m7 -Oz -DNDEBUG"
    )
    mcux_add_armgcc_configuration(
        AS  "-mcpu=cortex-m7 -mthumb -D__STARTUP_CLEAR_BSS -DNDEBUG"
        CC  "-mcpu=cortex-m7 -mthumb -MMD -MP -Os -DCPU_MIMXRT1176DVMAB_cm7 -DCPU_IS_ARM_CORTEX_M7=1 -DXIP_EXTERNAL_FLASH=1 -DXIP_BOOT_HEADER_ENABLE=1 -DNDEBUG"
        CX  "-mcpu=cortex-m7 -mthumb -MMD -MP -Os -DNDEBUG"
    )
endif()

if(CONFIG_MCUX_PRJSEG_evkbmimxrt1170_cm4_kboot_options)
    mcux_add_iar_configuration(
        AS  "-DNDEBUG"
        CC  "-Ohz -DCPU_MIMXRT1176DVMAB_cm4 -DCPU_IS_ARM_CORTEX_M4=1 -DXIP_EXTERNAL_FLASH=1 -DXIP_BOOT_HEADER_ENABLE=1 -DNDEBUG"
        CX  "-DNDEBUG"
    )
    mcux_add_mdk_configuration(
        AS  "-mcpu=cortex-m4 -DNDEBUG"
        CC  "-mcpu=cortex-m4 -Oz -DCPU_MIMXRT1176DVMAB_cm4 -DCPU_IS_ARM_CORTEX_M4=1 -DXIP_EXTERNAL_FLASH=1 -DXIP_BOOT_HEADER_ENABLE=1 -DNDEBUG"
        CX  "-mcpu=cortex-m4 -Oz -DNDEBUG"
    )
    mcux_add_armgcc_configuration(
        AS  "-mcpu=cortex-m4 -mthumb -D__STARTUP_CLEAR_BSS -DNDEBUG"
        CC  "-mcpu=cortex-m4 -mthumb -MMD -MP -Os -DCPU_MIMXRT1176DVMAB_cm4 -DCPU_IS_ARM_CORTEX_M4=1 -DXIP_EXTERNAL_FLASH=1 -DXIP_BOOT_HEADER_ENABLE=1 -DNDEBUG"
        CX  "-mcpu=cortex-m4 -mthumb -MMD -MP -Os -DNDEBUG"
    )
endif()

if(CONFIG_MCUX_PRJSEG_evkcmimxrt1060_kboot_options)
    mcux_add_iar_configuration(
        AS  ""
        CC  "-Ohz -DCPU_MIMXRT1062DVL6B -DCPU_IS_ARM_CORTEX_M7=1 -DXIP_EXTERNAL_FLASH=1 -DNDEBUG"
        CX  "-DNDEBUG"
    )
    mcux_add_mdk_configuration(
        AS  "-mcpu=cortex-m7 -DNDEBUG"
        CC  "-mcpu=cortex-m7 -Oz -DCPU_MIMXRT1062DVL6B -DCPU_IS_ARM_CORTEX_M7=1 -DXIP_EXTERNAL_FLASH=1 -DNDEBUG"
        CX  "-mcpu=cortex-m7 -Oz -DNDEBUG"
    )
    mcux_add_armgcc_configuration(
        AS  "-mthumb -D__STARTUP_CLEAR_BSS -DNDEBUG"
        CC  "-mthumb -MMD -MP -Os -DCPU_MIMXRT1062DVL6B -DCPU_IS_ARM_CORTEX_M7=1 -DXIP_EXTERNAL_FLASH=1 -DNDEBUG"
        CX  "-mthumb -MMD -MP -Os -DNDEBUG"
    )
endif()

if(CONFIG_MCUX_PRJSEG_evkmimxrt1010_kboot_options)
    mcux_add_iar_configuration(
        AS  ""
        CC  "-Ohz -DCPU_MIMXRT1011DAE5A -DCPU_IS_ARM_CORTEX_M7=1"
        CX  ""
    )
    mcux_add_mdk_configuration(
        AS  "-mcpu=cortex-m7"
        CC  "-mcpu=cortex-m7 -DCPU_MIMXRT1011DAE5A -DCPU_IS_ARM_CORTEX_M7=1"
        CX  "-mcpu=cortex-m7"
    )
    mcux_add_armgcc_configuration(
        AS  "-mcpu=cortex-m7 -mthumb"
        CC  "-mcpu=cortex-m7 -Wall -mthumb -MMD -MP -DCPU_MIMXRT1011DAE5A -DCPU_IS_ARM_CORTEX_M7=1 -Wno-comment"
        CX  "-mcpu=cortex-m7 -Wall -mthumb -MMD -MP -DCPU_MIMXRT1011DAE5A"
    )
endif()

if(CONFIG_MCUX_PRJSEG_evkmimxrt1015_kboot_options)
    mcux_add_iar_configuration(
        AS  ""
        CC  "-DCPU_MIMXRT1015DAF5A -DCPU_IS_ARM_CORTEX_M7=1"
        CX  ""
    )
    mcux_add_mdk_configuration(
        AS  "-mcpu=cortex-m7"
        CC  "-mcpu=cortex-m7 -DCPU_MIMXRT1015DAF5A -DCPU_IS_ARM_CORTEX_M7=1"
        CX  "-mcpu=cortex-m7"
    )
    mcux_add_armgcc_configuration(
        AS  "-mcpu=cortex-m7 -mfloat-abi=hard -mfpu=fpv5-d16 -mthumb"
        CC  "-mcpu=cortex-m7 -mfloat-abi=hard -mfpu=fpv5-d16 -mthumb -MMD -MP -DCPU_MIMXRT1015DAF5A -DCPU_IS_ARM_CORTEX_M7=1"
        CX  "-mcpu=cortex-m7 -mfloat-abi=hard -mfpu=fpv5-d16 -mthumb -MMD -MP"
    )
endif()

if(CONFIG_MCUX_PRJSEG_evkmimxrt1020_kboot_options)
    mcux_add_iar_configuration(
        AS  "-DNDEBUG"
        CC  "-Ohz -DCPU_MIMXRT1021DAG5A -DCPU_IS_ARM_CORTEX_M7=1 -DNDEBUG"
        CX  "-DNDEBUG"
    )
    mcux_add_mdk_configuration(
        AS  "-mcpu=cortex-m7 -DNDEBUG"
        CC  "-mcpu=cortex-m7 -Oz -DCPU_MIMXRT1021DAG5A -DCPU_IS_ARM_CORTEX_M7=1 -DNDEBUG"
        CX  "-mcpu=cortex-m7 -Oz -DNDEBUG"
    )
    mcux_add_armgcc_configuration(
        AS  "-mcpu=cortex-m7 -mfloat-abi=hard -mfpu=fpv5-d16 -mthumb -D__STARTUP_CLEAR_BSS -DNDEBUG"
        CC  "-mcpu=cortex-m7 -mfloat-abi=hard -mfpu=fpv5-d16 -mthumb -MMD -MP -Os -DCPU_MIMXRT1021DAG5A -DCPU_IS_ARM_CORTEX_M7=1 -DNDEBUG"
        CX  "-mcpu=cortex-m7 -mfloat-abi=hard -mfpu=fpv5-d16 -mthumb -MMD -MP -Os -DNDEBUG"
    )
endif()

if(CONFIG_MCUX_PRJSEG_evkmimxrt1024_kboot_options)
    mcux_add_iar_configuration(
        AS  "-DNDEBUG"
        CC  "-Ohz -DCPU_MIMXRT1024DAG5A -DCPU_IS_ARM_CORTEX_M7=1 -DXIP_EXTERNAL_FLASH=1 -DXIP_BOOT_HEADER_ENABLE=1 -DNDEBUG"
        CX  "-DNDEBUG"
    )
    mcux_add_mdk_configuration(
        AS  "-mcpu=cortex-m7 -DNDEBUG"
        CC  "-mcpu=cortex-m7 -Oz -DCPU_MIMXRT1024DAG5A -DCPU_IS_ARM_CORTEX_M7=1 -DXIP_EXTERNAL_FLASH=1 -DXIP_BOOT_HEADER_ENABLE=1 -DNDEBUG"
        CX  "-mcpu=cortex-m7 -Oz -DNDEBUG"
    )
    mcux_add_armgcc_configuration(
        AS  "-mcpu=cortex-m7 -mfloat-abi=hard -mfpu=fpv5-d16 -mthumb -D__STARTUP_CLEAR_BSS -DNDEBUG"
        CC  "-mcpu=cortex-m7 -mfloat-abi=hard -mfpu=fpv5-d16 -mthumb -MMD -MP -Os -DCPU_MIMXRT1024DAG5A -DCPU_IS_ARM_CORTEX_M7=1 -DXIP_EXTERNAL_FLASH=1 -DXIP_BOOT_HEADER_ENABLE=1 -DNDEBUG"
        CX  "-mcpu=cortex-m7 -mfloat-abi=hard -mfpu=fpv5-d16 -mthumb -MMD -MP -Os -DNDEBUG"
    )
endif()

if(CONFIG_MCUX_PRJSEG_evkmimxrt1040_kboot_options)
    mcux_add_iar_configuration(
        AS  "-DNDEBUG"
        CC  "-Ohz -DCPU_MIMXRT1042XJM5B -DCPU_IS_ARM_CORTEX_M7=1 -DXIP_EXTERNAL_FLASH=1 -DNDEBUG"
        CX  "-DCPU_MIMXRT1042XJM5B -DNDEBUG"
    )
    mcux_add_mdk_configuration(
        AS  "-mcpu=cortex-m7 -DNDEBUG"
        CC  "-mcpu=cortex-m7 -Oz -DCPU_MIMXRT1042XJM5B -DCPU_IS_ARM_CORTEX_M7=1 -DXIP_EXTERNAL_FLASH=1 -DNDEBUG"
        CX  "-mcpu=cortex-m7 -Oz -DCPU_MIMXRT1042XJM5B -DNDEBUG"
    )
    mcux_add_armgcc_configuration(
        AS  "-mcpu=cortex-m7 -mfloat-abi=hard -mfpu=fpv5-d16 -mthumb -D__STARTUP_CLEAR_BSS -DNDEBUG"
        CC  "-mcpu=cortex-m7 -mfloat-abi=hard -mfpu=fpv5-d16 -mthumb -MMD -MP -Os -DCPU_MIMXRT1042XJM5B -DCPU_IS_ARM_CORTEX_M7=1 -DXIP_EXTERNAL_FLASH=1 -DNDEBUG"
        CX  "-mcpu=cortex-m7 -mfloat-abi=hard -mfpu=fpv5-d16 -mthumb -MMD -MP -Os -DCPU_MIMXRT1042XJM5B -DNDEBUG"
    )
endif()

if(CONFIG_MCUX_PRJSEG_evkmimxrt1060_kboot_options)
    mcux_add_iar_configuration(
        AS  "--cpu=cortex-m7 --fpu none -DNDEBUG"
        CC  "--cpu=cortex-m7 --fpu none -Om -DCPU_MIMXRT1062DVL6A -DCPU_IS_ARM_CORTEX_M7=1 -DXIP_EXTERNAL_FLASH=1 -DXIP_BOOT_HEADER_ENABLE=1 -DNDEBUG"
        CX  "--cpu=cortex-m7 --fpu none -DNDEBUG"
    )
    mcux_add_mdk_configuration(
        AS  "-mcpu=cortex-m7 -DNDEBUG"
        CC  "-mcpu=cortex-m7 -Oz -DCPU_MIMXRT1062DVL6A -DCPU_IS_ARM_CORTEX_M7=1 -DXIP_EXTERNAL_FLASH=1 -DXIP_BOOT_HEADER_ENABLE=1 -DNDEBUG"
        CX  "-mcpu=cortex-m7 -Oz -DNDEBUG"
    )
    mcux_add_armgcc_configuration(
        AS  "-mcpu=cortex-m7 -mfloat-abi=hard -mfpu=fpv5-d16 -mthumb -D__STARTUP_CLEAR_BSS -DNDEBUG"
        CC  "-mcpu=cortex-m7 -mfloat-abi=hard -mfpu=fpv5-d16 -mthumb -MMD -MP -Os -DCPU_MIMXRT1062DVL6A -DCPU_IS_ARM_CORTEX_M7=1 -DXIP_EXTERNAL_FLASH=1 -DXIP_BOOT_HEADER_ENABLE=1 -DNDEBUG"
        CX  "-mcpu=cortex-m7 -mfloat-abi=hard -mfpu=fpv5-d16 -mthumb -MMD -MP -Os -DNDEBUG"
    )
endif()

if(CONFIG_MCUX_PRJSEG_evkmimxrt1064_kboot_options)
    mcux_add_iar_configuration(
        AS  ""
        CC  "-DCPU_MIMXRT1064DVL6A -DCPU_IS_ARM_CORTEX_M7=1"
        CX  ""
    )
    mcux_add_mdk_configuration(
        AS  "-mcpu=cortex-m7"
        CC  "-mcpu=cortex-m7 -DCPU_MIMXRT1064DVL6A -DCPU_IS_ARM_CORTEX_M7=1"
        CX  "-mcpu=cortex-m7"
    )
    mcux_add_armgcc_configuration(
        AS  "-mcpu=cortex-m7 -mfloat-abi=hard -mfpu=fpv5-d16 -mthumb"
        CC  "-mcpu=cortex-m7 -mfloat-abi=hard -mfpu=fpv5-d16 -mthumb -MMD -MP -DCPU_MIMXRT1064DVL6A -DCPU_IS_ARM_CORTEX_M7=1"
        CX  "-mcpu=cortex-m7 -mfloat-abi=hard -mfpu=fpv5-d16 -mthumb -MMD -MP"
    )
endif()

if(CONFIG_MCUX_PRJSEG_evkmimxrt1160_cm4_kboot_options)
    mcux_add_iar_configuration(
        AS  "-DNDEBUG"
        CC  "-Ohz -DCPU_MIMXRT1166DVM6A_cm4 -DCPU_IS_ARM_CORTEX_M4=1 -DXIP_EXTERNAL_FLASH=1 -DXIP_BOOT_HEADER_ENABLE=1 -DNDEBUG"
        CX  "-DNDEBUG"
    )
    mcux_add_mdk_configuration(
        AS  "-mcpu=cortex-m4 -DNDEBUG"
        CC  "-mcpu=cortex-m4 -Oz -DCPU_MIMXRT1166DVM6A_cm4 -DCPU_IS_ARM_CORTEX_M4=1 -DXIP_EXTERNAL_FLASH=1 -DXIP_BOOT_HEADER_ENABLE=1 -DNDEBUG"
        CX  "-mcpu=cortex-m4 -Oz -DNDEBUG"
    )
    mcux_add_armgcc_configuration(
        AS  "-mcpu=cortex-m4 -mthumb -D__STARTUP_CLEAR_BSS -DNDEBUG"
        CC  "-mcpu=cortex-m4 -mthumb -MMD -MP -Os -DCPU_MIMXRT1166DVM6A_cm4 -DCPU_IS_ARM_CORTEX_M4=1 -DXIP_EXTERNAL_FLASH=1 -DXIP_BOOT_HEADER_ENABLE=1 -DNDEBUG"
        CX  "-mcpu=cortex-m4 -mthumb -MMD -MP -Os -DNDEBUG"
    )
endif()
if(CONFIG_MCUX_PRJSEG_evkmimxrt1160_cm7_kboot_options)
    mcux_add_iar_configuration(
        AS  "-DNDEBUG"
        CC  "-Ohz -DCPU_MIMXRT1166DVM6A_cm7 -DCPU_IS_ARM_CORTEX_M7=1 -DXIP_EXTERNAL_FLASH=1 -DXIP_BOOT_HEADER_ENABLE=1 -DNDEBUG"
        CX  "-DNDEBUG"
    )
    mcux_add_mdk_configuration(
        AS  "-mcpu=cortex-m7 -DNDEBUG"
        CC  "-mcpu=cortex-m7 -Oz -DCPU_MIMXRT1166DVM6A_cm7 -DCPU_IS_ARM_CORTEX_M7=1 -DXIP_EXTERNAL_FLASH=1 -DXIP_BOOT_HEADER_ENABLE=1 -DNDEBUG"
        CX  "-mcpu=cortex-m7 -Oz -DNDEBUG"
    )
    mcux_add_armgcc_configuration(
        AS  "-mcpu=cortex-m7 -mthumb -D__STARTUP_CLEAR_BSS -DNDEBUG"
        CC  "-mcpu=cortex-m7 -mthumb -MMD -MP -Os -DCPU_MIMXRT1166DVM6A_cm7 -DCPU_IS_ARM_CORTEX_M7=1 -DXIP_EXTERNAL_FLASH=1 -DXIP_BOOT_HEADER_ENABLE=1 -DNDEBUG"
        CX  "-mcpu=cortex-m7 -mthumb -MMD -MP -Os -DNDEBUG"
    )
endif()

if(CONFIG_MCUX_PRJSEG_evkmimxrt1170_kboot_options)
    mcux_add_iar_configuration(
        AS  "--cpu=cortex-m7 --fpu none -DNDEBUG"
        CC  "--cpu=cortex-m7 --fpu none -Om -DCPU_MIMXRT1176DVMAA_cm7 -DCPU_IS_ARM_CORTEX_M7=1 -DXIP_EXTERNAL_FLASH=1 -DXIP_BOOT_HEADER_ENABLE=1 -DNDEBUG"
        CX  "--cpu=cortex-m7 --fpu none -DNDEBUG"
    )
    mcux_add_mdk_configuration(
        AS  "-mcpu=cortex-m7 -DNDEBUG"
        CC  "-mcpu=cortex-m7 -Oz -DCPU_MIMXRT1176DVMAA_cm7 -DCPU_IS_ARM_CORTEX_M7=1 -DXIP_EXTERNAL_FLASH=1 -DXIP_BOOT_HEADER_ENABLE=1 -DNDEBUG"
        CX  "-mcpu=cortex-m7 -Oz -DNDEBUG"
    )
    mcux_add_armgcc_configuration(
        AS  "-mcpu=cortex-m7 -mfloat-abi=hard -mfpu=fpv5-d16 -mthumb -D__STARTUP_CLEAR_BSS -DNDEBUG"
        CC  "-mcpu=cortex-m7 -mfloat-abi=hard -mfpu=fpv5-d16 -mthumb -MMD -MP -Os -DCPU_MIMXRT1176DVMAA_cm7 -DCPU_IS_ARM_CORTEX_M7=1 -DXIP_EXTERNAL_FLASH=1 -DXIP_BOOT_HEADER_ENABLE=1 -DNDEBUG"
        CX  "-mcpu=cortex-m7 -mfloat-abi=hard -mfpu=fpv5-d16 -mthumb -MMD -MP -Os -DNDEBUG"
    )
endif()

if(CONFIG_MCUX_PRJSEG_evkmimxrt1180a_kboot_options)
    mcux_add_iar_configuration(
        AS  "--cpu=cortex-m33 --fpu=vfpv5_sp_d16 -DNDEBUG"
        CC  "--cpu=cortex-m33 --fpu=vfpv5_sp_d16 -Om -DCPU_MIMXRT1187CVM8B_cm33 -DROM_ENABLE_CMSE -DCPU_IS_ARM_CORTEX_M33=1 -DXIP_EXTERNAL_FLASH=1 -DXIP_BOOT_HEADER_ENABLE=0 -DNDEBUG"
        CX  "--cpu=cortex-m33 --fpu=vfpv5_sp_d16 -DNDEBUG"
    )
    mcux_add_mdk_configuration(
        AS  "-mcpu=cortex-m33 -DNDEBUG"
        CC  "-mcpu=cortex-m33 -mfpu=fpv5_sp_d16 -Oz -DCPU_MIMXRT1187CVM8B_cm33 -DROM_ENABLE_CMSE -DCPU_IS_ARM_CORTEX_M33=1 -DXIP_EXTERNAL_FLASH=1 -DXIP_BOOT_HEADER_ENABLE=0 -DNDEBUG"
        CX  "-mcpu=cortex-m33 -mfpu=fpv5_sp_d16 -Oz -DNDEBUG"
    )
    mcux_add_armgcc_configuration(
        AS  "-mcpu=cortex-m33 -mfloat-abi=hard -mfpu=fpv5-sp-d16 -mthumb -D__STARTUP_CLEAR_BSS -DNDEBUG"
        CC  "-mcpu=cortex-m33 -mfloat-abi=hard -mfpu=fpv5-sp-d16 -mthumb -MMD -MP -Os -DCPU_MIMXRT1187CVM8B_cm33 -DROM_ENABLE_CMSE -DCPU_IS_ARM_CORTEX_M33=1 -DXIP_EXTERNAL_FLASH=1 -DXIP_BOOT_HEADER_ENABLE=1 -DNDEBUG"
        CX  "-mcpu=cortex-m33 -mfloat-abi=hard -mfpu=fpv5-sp-d16 -mthumb -MMD -MP -Os -DNDEBUG"
    )
endif()

if(CONFIG_MCUX_PRJSEG_evkmimxrt1180_kboot_options)
    mcux_add_iar_configuration(
        AS  ""
        CC  "-Ohz -DCPU_MIMXRT1189CVM8C_cm33 -DCPU_IS_ARM_CORTEX_M33=1 -DROM_ENABLE_CMSE -DXIP_EXTERNAL_FLASH=1 -DXIP_BOOT_HEADER_ENABLE=0 -DNDEBUG"
        CX  "-DNDEBUG"
    )
    mcux_add_mdk_configuration(
        AS  "-mcpu=cortex-m33 -DNDEBUG"
        CC  "-mcpu=cortex-m33 -mfpu=fpv5_sp_d16 -Oz -DCPU_MIMXRT1189CVM8C_cm33 -DROM_ENABLE_CMSE -DCPU_IS_ARM_CORTEX_M33=1 -DXIP_EXTERNAL_FLASH=1 -DXIP_BOOT_HEADER_ENABLE=0 -DNDEBUG"
        CX  "-mcpu=cortex-m33 -mfpu=fpv5_sp_d16 -Oz -DNDEBUG"
    )
    mcux_add_armgcc_configuration(
        AS  "-mcpu=cortex-m33 -mfloat-abi=hard -mfpu=fpv5-sp-d16 -mthumb -D__STARTUP_CLEAR_BSS -DNDEBUG"
        CC  "-mcpu=cortex-m33 -mfloat-abi=hard -mfpu=fpv5-sp-d16 -mthumb -MMD -MP -Os -DCPU_MIMXRT1189CVM8C_cm33 -DROM_ENABLE_CMSE -DCPU_IS_ARM_CORTEX_M33=1 -DXIP_EXTERNAL_FLASH=1 -DXIP_BOOT_HEADER_ENABLE=1 -DNDEBUG"
        CX  "-mcpu=cortex-m33 -mfloat-abi=hard -mfpu=fpv5-sp-d16 -mthumb -MMD -MP -Os -DNDEBUG"
    )
endif()

if(CONFIG_MCUX_PRJSEG_frdmimxrt1186_kboot_options)
    mcux_add_iar_configuration(
        AS  ""
        CC  "-Ohz -DCPU_MIMXRT1186CVJ8C_cm33 -DROM_ENABLE_CMSE -DCPU_IS_ARM_CORTEX_M33=1 -DXIP_EXTERNAL_FLASH=1 -DXIP_BOOT_HEADER_ENABLE=0 -DNDEBUG"
        CX  "-DNDEBUG"
    )
    mcux_add_mdk_configuration(
        AS  "-mcpu=cortex-m33 -DNDEBUG"
        CC  "-mcpu=cortex-m33 -mfpu=fpv5_sp_d16 -Oz -DCPU_MIMXRT1186CVJ8C_cm33 -DROM_ENABLE_CMSE -DCPU_IS_ARM_CORTEX_M33=1 -DXIP_EXTERNAL_FLASH=1 -DXIP_BOOT_HEADER_ENABLE=0 -DNDEBUG"
        CX  "-mcpu=cortex-m33 -mfpu=fpv5_sp_d16 -Oz -DNDEBUG"
    )
    mcux_add_armgcc_configuration(
        AS  "-mcpu=cortex-m33 -mfloat-abi=hard -mfpu=fpv5-sp-d16 -mthumb -D__STARTUP_CLEAR_BSS -DNDEBUG"
        CC  "-mcpu=cortex-m33 -mfloat-abi=hard -mfpu=fpv5-sp-d16 -mthumb -MMD -MP -Os -DCPU_MIMXRT1186CVJ8C_cm33 -DROM_ENABLE_CMSE -DCPU_IS_ARM_CORTEX_M33=1 -DXIP_EXTERNAL_FLASH=1 -DXIP_BOOT_HEADER_ENABLE=1 -DNDEBUG"
        CX  "-mcpu=cortex-m33 -mfloat-abi=hard -mfpu=fpv5-sp-d16 -mthumb -MMD -MP -Os -DNDEBUG"
    )
endif()

if(CONFIG_MCUX_PRJSEG_frdmimxrt1150_kboot_options)
    mcux_add_iar_configuration(
        AS  "-DNDEBUG"
        CC  "-Ohz -DCPU_MIMXRT1152XHM8B -DCPU_IS_ARM_CORTEX_M7=1 -DXIP_EXTERNAL_FLASH=1 -DXIP_BOOT_HEADER_ENABLE=1 -DNDEBUG"
        CX  "-DNDEBUG"
    )
    mcux_add_mdk_configuration(
        AS  "-mcpu=cortex-m7 -DNDEBUG"
        CC  "-mcpu=cortex-m7 -Oz -DCPU_MIMXRT1152XHM8B -DCPU_IS_ARM_CORTEX_M7=1 -DXIP_EXTERNAL_FLASH=1 -DXIP_BOOT_HEADER_ENABLE=1 -DNDEBUG"
        CX  "-mcpu=cortex-m7 -Oz -DNDEBUG"
    )
    mcux_add_armgcc_configuration(
        AS  "-mcpu=cortex-m7 -mthumb -D__STARTUP_CLEAR_BSS -DNDEBUG"
        CC  "-mcpu=cortex-m7 -mthumb -MMD -MP -Os -DCPU_MIMXRT1152XHM8B -DCPU_IS_ARM_CORTEX_M7=1 -DXIP_EXTERNAL_FLASH=1 -DXIP_BOOT_HEADER_ENABLE=1 -DNDEBUG"
        CX  "-mcpu=cortex-m7 -mthumb -MMD -MP -Os -DNDEBUG"
    )
endif()

if(CONFIG_MCUX_PRJSEG_frdmk22f_kboot_options)
    mcux_add_iar_configuration(
        AS  ""
        CC  "-DCPU_MK22FN512VLH12 -DCPU_IS_ARM_CORTEX_M4=1"
        CX  ""
    )
    mcux_add_mdk_configuration(
        AS  "-mcpu=cortex-m4"
        CC  "-mcpu=cortex-m4 -mfpu=fpv4-sp-d16 -DCPU_MK22FN512VLH12 -DCPU_IS_ARM_CORTEX_M4=1"
        CX  "-mcpu=cortex-m4 -mfpu=fpv4-sp-d16"
    )
    mcux_add_armgcc_configuration(
        AS  "-mcpu=cortex-m4 -mfloat-abi=hard -mfpu=fpv4-sp-d16 -mthumb"
        CC  "-mcpu=cortex-m4 -mfloat-abi=hard -mfpu=fpv4-sp-d16 -mthumb -MMD -MP -DCPU_MK22FN512VLH12"
        CX  "-mcpu=cortex-m4 -mfloat-abi=hard -mfpu=fpv4-sp-d16 -mthumb -MMD -MP -DCPU_MK22FN512VLH12"
    )
endif()

if(CONFIG_MCUX_PRJSEG_frdmk32l2a4s_kboot_options)
    mcux_add_iar_configuration(
        AS  ""
        CC  " -DCPU_K32L2A41VLL1A -DCPU_IS_ARM_CORTEX_M0P=1"
        CX  ""
    )
    mcux_add_mdk_configuration(
        AS  "-mcpu=cortex-m0plus"
        CC  "-mcpu=cortex-m0plus -DCPU_K32L2A41VLL1A -DCPU_IS_ARM_CORTEX_M0P=1"
        CX  "-mcpu=cortex-m0plus"
    )
    mcux_add_armgcc_configuration(
        AS  "-mcpu=cortex-m0plus -mfloat-abi=soft -mthumb"
        CC  "-mcpu=cortex-m0plus -mfloat-abi=soft -mthumb -MMD -MP -DCPU_K32L2A41VLL1A"
        CX  "-mcpu=cortex-m0plus -mfloat-abi=soft -mthumb -MMD -MP"
    )
endif()

if(CONFIG_MCUX_PRJSEG_frdmk64f_kboot_options)
    mcux_add_iar_configuration(
        AS  "--cpu=cortex-m4 --fpu=None"
        CC  "--cpu=cortex-m4 --fpu=None -DCPU_MK64FN1M0VLL12 -DCPU_IS_ARM_CORTEX_M4=1"
        CX  "--cpu=cortex-m4 --fpu=None"
    )
    mcux_add_mdk_configuration(
        AS  "-mcpu=cortex-m4"
        CC  "-mcpu=cortex-m4 -mfpu=fpv4-sp-d16 -DCPU_MK64FN1M0VLL12 -DCPU_IS_ARM_CORTEX_M4=1"
        CX  "-mcpu=cortex-m4 -mfpu=fpv4-sp-d16"
    )
    mcux_add_armgcc_configuration(
        AS  "-mcpu=cortex-m4 -mfloat-abi=hard -mfpu=fpv4-sp-d16 -mthumb"
        CC  "-mcpu=cortex-m4 -Wall -mfloat-abi=hard -mfpu=fpv4-sp-d16 -mthumb -MMD -MP -DCPU_MK64FN1M0VLL12"
        CX  "-mcpu=cortex-m4 -Wall -mfloat-abi=hard -mfpu=fpv4-sp-d16 -mthumb -MMD -MP -DCPU_MK64FN1M0VLL12"
    )
endif()

if(CONFIG_MCUX_PRJSEG_frdmk66f_kboot_options)
    mcux_add_iar_configuration(
        AS  "--cpu=cortex-m4 --fpu=None"
        CC  "--cpu=cortex-m4 --fpu=None -DCPU_MK66FN2M0VMD18 -DCPU_IS_ARM_CORTEX_M4=1"
        CX  "--cpu=cortex-m4 --fpu=None"
    )
    mcux_add_mdk_configuration(
        AS  "-mcpu=cortex-m4"
        CC  "-mcpu=cortex-m4 -mfpu=fpv4-sp-d16 -DCPU_MK66FN2M0VMD18 -DCPU_IS_ARM_CORTEX_M4=1"
        CX  "-mcpu=cortex-m4 -mfpu=fpv4-sp-d16"
    )
    mcux_add_armgcc_configuration(
        AS  "-mcpu=cortex-m4 -mfloat-abi=hard -mfpu=fpv4-sp-d16 -mthumb"
        CC  "-mcpu=cortex-m4 -mfloat-abi=hard -mfpu=fpv4-sp-d16 -mthumb -MMD -MP -DCPU_MK66FN2M0VMD18"
        CX  "-mcpu=cortex-m4 -mfloat-abi=hard -mfpu=fpv4-sp-d16 -mthumb -MMD -MP -DCPU_MK66FN2M0VMD18"
    )
endif()

if(CONFIG_MCUX_PRJSEG_frdmk82f_kboot_options)
    mcux_add_iar_configuration(
        AS  "--cpu=cortex-m4 --fpu=None"
        CC  "--cpu=cortex-m4 --fpu=None -DCPU_MK82FN256VLL15 -DCPU_IS_ARM_CORTEX_M4=1"
        CX  "--cpu=cortex-m4 --fpu=None"
    )
    mcux_add_mdk_configuration(
        AS  "-mcpu=cortex-m4"
        CC  "-mcpu=cortex-m4 -mfpu=fpv4-sp-d16 -DCPU_MK82FN256VLL15 -DCPU_IS_ARM_CORTEX_M4=1"
        CX  "-mcpu=cortex-m4 -mfpu=fpv4-sp-d16"
    )
    mcux_add_armgcc_configuration(
        AS  "-mcpu=cortex-m4 -mfloat-abi=hard -mfpu=fpv4-sp-d16 -mthumb"
        CC  "-mcpu=cortex-m4 -mfloat-abi=hard -mfpu=fpv4-sp-d16 -mthumb -MMD -MP -DCPU_MK82FN256VLL15"
        CX  "-mcpu=cortex-m4 -mfloat-abi=hard -mfpu=fpv4-sp-d16 -mthumb -MMD -MP -DCPU_MK82FN256VLL15"
    )
endif()

if(CONFIG_MCUX_PRJSEG_frdmke16z_kboot_options)
    mcux_add_iar_configuration(
        AS  ""
        CC  "-DCPU_MKE16Z64VLF4 -DCPU_IS_ARM_CORTEX_M0P=1"
        CX  ""
    )
    mcux_add_mdk_configuration(
        AS  "-mcpu=cortex-m0plus"
        CC  "-mcpu=cortex-m0plus -DCPU_MKE16Z64VLF4 -DCPU_IS_ARM_CORTEX_M0P=1"
        CX  "-mcpu=cortex-m0plus"
    )
    mcux_add_armgcc_configuration(
        AS  "-mcpu=cortex-m0plus -mfloat-abi=soft -mthumb"
        CC  "-mcpu=cortex-m0plus -Wall -mfloat-abi=soft -mthumb -MMD -MP -DCPU_MKE16Z64VLF4"
        CX  "-mcpu=cortex-m0plus -Wall -mfloat-abi=soft -mthumb -MMD -MP"
    )
endif()

if(CONFIG_MCUX_PRJSEG_frdmke17z_kboot_options)
    mcux_add_iar_configuration(
        AS  ""
        CC  "-DCPU_MKE17Z256VLL7 -DCPU_IS_ARM_CORTEX_M0P=1"
        CX  ""
    )
    mcux_add_mdk_configuration(
        AS  "-mcpu=cortex-m0plus"
        CC  "-mcpu=cortex-m0plus -DCPU_MKE17Z256VLL7 -DCPU_IS_ARM_CORTEX_M0P=1"
        CX  "-mcpu=cortex-m0plus"
    )
    mcux_add_armgcc_configuration(
        AS  "-mcpu=cortex-m0plus -mfloat-abi=soft -mthumb"
        CC  "-mcpu=cortex-m0plus -mfloat-abi=soft -mthumb -MMD -MP -DCPU_MKE17Z256VLL7"
        CX  "-mcpu=cortex-m0plus -mfloat-abi=soft -mthumb -MMD -MP"
    )
endif()

if(CONFIG_MCUX_PRJSEG_frdmke17z512_kboot_options)
    mcux_add_iar_configuration(
        AS  ""
        CC  "-DCPU_MKE17Z512VLL9 -DCPU_IS_ARM_CORTEX_M0P=1"
        CX  ""
    )
    mcux_add_mdk_configuration(
        AS  "-mcpu=cortex-m0plus"
        CC  "-mcpu=cortex-m0plus -DCPU_MKE17Z512VLL9 -DCPU_IS_ARM_CORTEX_M0P=1"
        CX  "-mcpu=cortex-m0plus"
    )
    mcux_add_armgcc_configuration(
        AS  "-mcpu=cortex-m0plus -mfloat-abi=soft -mthumb"
        CC  "-mcpu=cortex-m0plus -mfloat-abi=soft -mthumb -MMD -MP -DCPU_MKE17Z512VLL9"
        CX  "-mcpu=cortex-m0plus -mfloat-abi=soft -mthumb -MMD -MP"
    )
endif()

if(CONFIG_MCUX_PRJSEG_frdmkl28z_kboot_options)
    mcux_add_iar_configuration(
        AS  "--cpu=cortex-M0+ --fpu=None"
        CC  "--cpu=cortex-M0+ --fpu=None -DCPU_MKL28Z512VLL7 -DCPU_IS_ARM_CORTEX_M0P=1"
        CX  "--cpu=cortex-M0+ --fpu=None"
    )
    mcux_add_mdk_configuration(
        AS  "--cpu Cortex-M0plus"
        CC  "--cpu Cortex-M0plus -DCPU_MKL28Z512VLL7 -DCPU_IS_ARM_CORTEX_M0P=1"
        CX  "--cpu Cortex-M0plus"
    )
endif()

if(CONFIG_MCUX_PRJSEG_frdmkl82z_kboot_options)
    mcux_add_iar_configuration(
        AS  "--cpu=cortex-M0+ --fpu=None"
        CC  "--cpu=cortex-M0+ --fpu=None -DCPU_MKL82Z128VLK7 -DCPU_IS_ARM_CORTEX_M0P=1"
        CX  "--cpu=cortex-M0+ --fpu=None"
    )
    mcux_add_mdk_configuration(
        AS  "--cpu Cortex-M0plus"
        CC  "--cpu Cortex-M0plus -DCPU_MKL82Z128VLK7 -DCPU_IS_ARM_CORTEX_M0P=1"
        CX  "--cpu Cortex-M0plus"
    )
endif()

if(CONFIG_MCUX_PRJSEG_frdmkv11z_kboot_options)
    mcux_add_iar_configuration(
        AS  "--cpu=cortex-M0+ --fpu=None"
        CC  "--cpu=cortex-M0+ --fpu=None -DCPU_MKV11Z128VLH7 -DCPU_IS_ARM_CORTEX_M0P=1"
        CX  "--cpu=cortex-M0+ --fpu=None"
    )
    mcux_add_mdk_configuration(
        AS  "-mcpu=cortex-m0plus"
        CC  "-mcpu=cortex-m0plus -DCPU_MKV11Z128VLH7 -DCPU_IS_ARM_CORTEX_M0P=1"
        CX  "-mcpu=cortex-m0plus"
    )
    mcux_add_armgcc_configuration(
        AS  "-mcpu=cortex-m0plus -mfloat-abi=soft -mthumb"
        CC  "-mcpu=cortex-m0plus -mfloat-abi=soft -mthumb -MMD -MP -DCPU_MKV11Z128VLH7"
        CX  "-mcpu=cortex-m0plus -mfloat-abi=soft -mthumb -MMD -MP"
    )
endif()

if(CONFIG_MCUX_PRJSEG_frdmkv31f_kboot_options)
    mcux_add_iar_configuration(
        AS  "--cpu=cortex-m4 --fpu=None"
        CC  "--cpu=cortex-m4 --fpu=None -DCPU_MKV31F512VLL12"
        CX  "--cpu=cortex-m4 --fpu=None"
    )
    mcux_add_mdk_configuration(
        AS  "-mcpu=cortex-m4"
        CC  "-mcpu=cortex-m4 -mfpu=fpv4-sp-d16 -DCPU_MKV31F512VLL12"
        CX  "-mcpu=cortex-m4 -mfpu=fpv4-sp-d16"
    )
    mcux_add_armgcc_configuration(
        AS  "-mcpu=cortex-m4 -mfloat-abi=hard -mfpu=fpv4-sp-d16 -mthumb"
        CC  "-mcpu=cortex-m4 -mfloat-abi=hard -mfpu=fpv4-sp-d16 -mthumb -MMD -MP -DCPU_MKV31F512VLL12"
        CX  "-mcpu=cortex-m4 -mfloat-abi=hard -mfpu=fpv4-sp-d16 -mthumb -MMD -MP"
    )
endif()

if(CONFIG_MCUX_PRJSEG_lpcxpresso54018_kboot_options)
    mcux_add_configuration(
        CC  "-DCPU_LPC54018JET180"
    )
    mcux_add_iar_configuration(
        AS  "--cpu=cortex-m4 --fpu=vfpv4_sp_d16"
        CC  "--cpu=cortex-m4 --fpu=vfpv4_sp_d16 -DCPU_LPC54018 -DCPU_IS_ARM_CORTEX_M4=1 -DUSB_STACK_USE_DEDICATED_RAM=1"
        CX  "--cpu=cortex-m4 --fpu=vfpv4_sp_d16"
    )
    mcux_add_mdk_configuration(
        AS  "--cpu Cortex-M4.fp"
        CC  "--cpu Cortex-M4.fp -DCPU_LPC54018 -DCPU_IS_ARM_CORTEX_M4=1 -DUSB_STACK_USE_DEDICATED_RAM=1"
        CX  "--cpu Cortex-M4.fp"
    )
    mcux_add_armgcc_configuration(
        AS  "-mcpu=cortex-m4 -mfloat-abi=hard -mfpu=fpv4-sp-d16 -mthumb"
        CC  "-mcpu=cortex-m4 -mfloat-abi=hard -mfpu=fpv4-sp-d16 -mthumb -MMD -MP -DCPU_LPC54018 -DCPU_IS_ARM_CORTEX_M4=1 -DUSB_STACK_USE_DEDICATED_RAM=1"
        CX  "-mcpu=cortex-m4 -mfloat-abi=hard -mfpu=fpv4-sp-d16 -mthumb -MMD -MP"
    )
endif()

if(CONFIG_MCUX_PRJSEG_lpcxpresso54s018_kboot_options)
    mcux_add_configuration(
        CC  "-DCPU_LPC54S018JET180"
    )
    mcux_add_iar_configuration(
        AS  ""
        CC  "-DCPU_LPC54S018 -DCPU_IS_ARM_CORTEX_M4=1 -DUSB_STACK_USE_DEDICATED_RAM=1"
        CX  ""
    )
    mcux_add_mdk_configuration(
        AS  ""
        CC  "-DCPU_LPC54S018 -DCPU_IS_ARM_CORTEX_M4=1 -DUSB_STACK_USE_DEDICATED_RAM=1"
        CX  ""
    )
    mcux_add_armgcc_configuration(
        AS  "-mcpu=cortex-m4 -mfloat-abi=hard -mfpu=fpv4-sp-d16 -mthumb"
        CC  "-mcpu=cortex-m4 -mfloat-abi=hard -mfpu=fpv4-sp-d16 -mthumb -MMD -MP -DCPU_LPC54S018 -DCPU_IS_ARM_CORTEX_M4=1 -DUSB_STACK_USE_DEDICATED_RAM=1"
        CX  "-mcpu=cortex-m4 -mfloat-abi=hard -mfpu=fpv4-sp-d16 -mthumb -MMD -MP"
    )
endif()

if(CONFIG_MCUX_PRJSEG_lpcxpresso54s018m_kboot_options)
    mcux_add_configuration(
        CC  "-DCPU_LPC54S018J4MET180"
    )
    mcux_add_iar_configuration(
        AS  ""
        CC  "-DCPU_LPC54S018M -DCPU_IS_ARM_CORTEX_M4=1 -DUSB_STACK_USE_DEDICATED_RAM=1"
        CX  ""
    )
    mcux_add_mdk_configuration(
        AS  ""
        CC  "-DCPU_LPC54S018M -DCPU_IS_ARM_CORTEX_M4=1 -DUSB_STACK_USE_DEDICATED_RAM=1"
        CX  ""
    )
    mcux_add_armgcc_configuration(
        AS  "-mcpu=cortex-m4 -mfloat-abi=hard -mfpu=fpv4-sp-d16 -mthumb"
        CC  "-mcpu=cortex-m4 -mfloat-abi=hard -mfpu=fpv4-sp-d16 -mthumb -MMD -MP -DCPU_LPC54S018M -DCPU_IS_ARM_CORTEX_M4=1 -DUSB_STACK_USE_DEDICATED_RAM=1"
        CX  "-mcpu=cortex-m4 -mfloat-abi=hard -mfpu=fpv4-sp-d16 -mthumb -MMD -MP"
    )
endif()

if(CONFIG_MCUX_PRJSEG_mapsks22_kboot_options)
    mcux_add_iar_configuration(
        AS  "--cpu=cortex-m4 --fpu=None"
        CC  "--cpu=cortex-m4 --fpu=None -DCPU_MKS22FN256VLL12 -DCPU_IS_ARM_CORTEX_M4=1"
        CX  "--cpu=cortex-m4 --fpu=None"
    )
    mcux_add_mdk_configuration(
        AS  "--cpu Cortex-M4.fp"
        CC  "--cpu Cortex-M4.fp -DCPU_MKS22FN256VLL12 -DCPU_IS_ARM_CORTEX_M4=1"
        CX  "--cpu Cortex-M4.fp"
    )
endif()

if(CONFIG_MCUX_PRJSEG_twrk22f120m_kboot_options)
    mcux_add_iar_configuration(
        AS  "--cpu=cortex-m4 --fpu=None"
        CC  "--cpu=cortex-m4 --fpu=None -DCPU_MK22FN512VDC12 -DCPU_IS_ARM_CORTEX_M4=1"
        CX  "--cpu=cortex-m4 --fpu=None"
    )
    mcux_add_mdk_configuration(
        AS  "-mcpu=cortex-m4"
        CC  "-mcpu=cortex-m4 -mfpu=fpv4-sp-d16 -DCPU_MK22FN512VDC12 -DCPU_IS_ARM_CORTEX_M4=1"
        CX  "-mcpu=cortex-m4 -mfpu=fpv4-sp-d16"
    )
    mcux_add_armgcc_configuration(
        AS  "-mcpu=cortex-m4 -mfloat-abi=hard -mfpu=fpv4-sp-d16 -mthumb"
        CC  "-mcpu=cortex-m4 -mfloat-abi=hard -mfpu=fpv4-sp-d16 -mthumb -MMD -MP -DCPU_MK22FN512VDC12"
        CX  "-mcpu=cortex-m4 -mfloat-abi=hard -mfpu=fpv4-sp-d16 -mthumb -MMD -MP"
    )
endif()

if(CONFIG_MCUX_PRJSEG_twrk64f120m_kboot_options)
    mcux_add_iar_configuration(
        AS  "--cpu=cortex-m4 --fpu=None"
        CC  "--cpu=cortex-m4 --fpu=None -DCPU_MK64FN1M0VMD12 -DCPU_IS_ARM_CORTEX_M4=1"
        CX  "--cpu=cortex-m4 --fpu=None"
    )
    mcux_add_mdk_configuration(
        AS  "-mcpu=cortex-m4"
        CC  "-mcpu=cortex-m4 -mfpu=fpv4-sp-d16 -DCPU_MK64FN1M0VMD12 -DCPU_IS_ARM_CORTEX_M4=1"
        CX  "-mcpu=cortex-m4 -mfpu=fpv4-sp-d16"
    )
    mcux_add_armgcc_configuration(
        AS  "-mcpu=cortex-m4 -mfloat-abi=hard -mfpu=fpv4-sp-d16 -mthumb"
        CC  "-mcpu=cortex-m4 -mfloat-abi=hard -mfpu=fpv4-sp-d16 -mthumb -MMD -MP -DCPU_MK64FN1M0VMD12"
        CX  "-mcpu=cortex-m4 -mfloat-abi=hard -mfpu=fpv4-sp-d16 -mthumb -MMD -MP"
    )
endif()

if(CONFIG_MCUX_PRJSEG_twrk65f180m_kboot_options)
    mcux_add_iar_configuration(
        AS  "--cpu=cortex-m4 --fpu=None"
        CC  "--cpu=cortex-m4 --fpu=None -DCPU_MK65FN2M0VMI18 -DCPU_IS_ARM_CORTEX_M4=1"
        CX  "--cpu=cortex-m4 --fpu=None"
    )
    mcux_add_mdk_configuration(
        AS  "-mcpu=cortex-m4"
        CC  "-mcpu=cortex-m4 -mfpu=fpv4-sp-d16 -DCPU_MK65FN2M0VMI18 -DCPU_IS_ARM_CORTEX_M4=1"
        CX  "-mcpu=cortex-m4 -mfpu=fpv4-sp-d16"
    )
    mcux_add_armgcc_configuration(
        AS  "-mcpu=cortex-m4 -mfloat-abi=hard -mfpu=fpv4-sp-d16 -mthumb"
        CC  "-mcpu=cortex-m4 -mfloat-abi=hard -mfpu=fpv4-sp-d16 -mthumb -MMD -MP -DCPU_MK65FN2M0VMI18"
        CX  "-mcpu=cortex-m4 -mfloat-abi=hard -mfpu=fpv4-sp-d16 -mthumb -MMD -MP"
    )
endif()

if(CONFIG_MCUX_PRJSEG_twrk80f150m_kboot_options)
    mcux_add_iar_configuration(
        AS  "--cpu=cortex-m4 --fpu=None"
        CC  "--cpu=cortex-m4 --fpu=None -DCPU_MK80FN256VDC15 -DCPU_IS_ARM_CORTEX_M4=1"
        CX  "--cpu=cortex-m4 --fpu=None"
    )
    mcux_add_mdk_configuration(
        AS  "-mcpu=cortex-m4"
        CC  "-mcpu=cortex-m4 -mfpu=fpv4-sp-d16 -DCPU_MK80FN256VDC15 -DCPU_IS_ARM_CORTEX_M4=1"
        CX  "-mcpu=cortex-m4 -mfpu=fpv4-sp-d16"
    )
    mcux_add_armgcc_configuration(
        AS  "-mcpu=cortex-m4 -mfloat-abi=hard -mfpu=fpv4-sp-d16 -mthumb"
        CC  "-mcpu=cortex-m4 -mfloat-abi=hard -mfpu=fpv4-sp-d16 -mthumb -MMD -MP -DCPU_MK80FN256VDC15"
        CX  "-mcpu=cortex-m4 -mfloat-abi=hard -mfpu=fpv4-sp-d16 -mthumb -MMD -MP"
    )
endif()

if(CONFIG_MCUX_PRJSEG_twrkl28z72m_kboot_options)
    mcux_add_iar_configuration(
        AS  "--cpu=cortex-M0+ --fpu=None"
        CC  "--cpu=cortex-M0+ --fpu=None -DCPU_MKL28Z512VLL7 -DCPU_IS_ARM_CORTEX_M0P=1"
        CX  "--cpu=cortex-M0+ --fpu=None"
    )
    mcux_add_mdk_configuration(
        AS  "--cpu Cortex-M0plus"
        CC  "--cpu Cortex-M0+ -DCPU_MKL28Z512VLL7 -DCPU_IS_ARM_CORTEX_M0P=1"
        CX  "--cpu Cortex-M0plus"
    )
endif()

if(CONFIG_MCUX_PRJSEG_twrkl82z72m_kboot_options)
    mcux_add_iar_configuration(
        AS  "--cpu=cortex-M0+ --fpu=None"
        CC  "--cpu=cortex-M0+ --fpu=None -DCPU_MKL82Z128VMC7 -DCPU_IS_ARM_CORTEX_M0P=1"
        CX  "--cpu=cortex-M0+ --fpu=None"
    )
    mcux_add_mdk_configuration(
        AS  "--cpu Cortex-M0plus"
        CC  "--cpu Cortex-M0plus -DCPU_MKL82Z128VMC7 -DCPU_IS_ARM_CORTEX_M0P=1"
        CX  "--cpu Cortex-M0plus"
    )
endif()

if(CONFIG_MCUX_PRJSEG_twrkm35z75m_kboot_options)
    mcux_add_iar_configuration(
        AS  ""
        CC  "-DCPU_MKM35Z512VLQ7 -DCPU_IS_ARM_CORTEX_M0P=1"
        CX  ""
    )
    mcux_add_mdk_configuration(
        AS  "-mcpu=cortex-m0plus"
        CC  "-mcpu=cortex-m0plus -DCPU_MKM35Z512VLQ7 -DCPU_IS_ARM_CORTEX_M0P=1"
        CX  "-mcpu=cortex-m0plus"
    )
    mcux_add_armgcc_configuration(
        AS  "-mcpu=cortex-m0plus -mfloat-abi=soft -mthumb"
        CC  "-mcpu=cortex-m0plus -mfloat-abi=soft -mthumb -MMD -MP -DCPU_MKM35Z512VLQ7"
        CX  "-mcpu=cortex-m0plus -mfloat-abi=soft -mthumb -MMD -MP"
    )
endif()

if(CONFIG_MCUX_PRJSEG_twrkv11z75m_kboot_options)
    mcux_add_iar_configuration(
        AS  "--cpu=cortex-M0+ --fpu=None"
        CC  "--cpu=cortex-M0+ --fpu=None -DCPU_MKV11Z128VLH7 -DCPU_IS_ARM_CORTEX_M0P=1"
        CX  "--cpu=cortex-M0+ --fpu=None"
    )
    mcux_add_mdk_configuration(
        AS  "-mcpu=cortex-m0plus"
        CC  "-mcpu=cortex-m0plus -DCPU_MKV11Z128VLH7 -DCPU_IS_ARM_CORTEX_M0P=1"
        CX  "-mcpu=cortex-m0plus"
    )
    mcux_add_armgcc_configuration(
        AS  "-mcpu=cortex-m0plus -mfloat-abi=soft -mthumb"
        CC  "-mcpu=cortex-m0plus -mfloat-abi=soft -mthumb -MMD -MP -DCPU_MKV11Z128VLH7"
        CX  "-mcpu=cortex-m0plus -mfloat-abi=soft -mthumb -MMD -MP"
    )
endif()

if(CONFIG_MCUX_PRJSEG_twrkv31f120m_kboot_options)
    mcux_add_iar_configuration(
        AS  "--cpu=cortex-m4 --fpu=None"
        CC  "--cpu=cortex-m4 --fpu=None -DCPU_MKV31F512VLL12"
        CX  "--cpu=cortex-m4 --fpu=None"
    )
    mcux_add_mdk_configuration(
        AS  "-mcpu=cortex-m4"
        CC  "-mcpu=cortex-m4 -mfpu=fpv4-sp-d16 -DCPU_MKV31F512VLL12"
        CX  "-mcpu=cortex-m4 -mfpu=fpv4-sp-d16"
    )
    mcux_add_armgcc_configuration(
        AS  "-mcpu=cortex-m4 -mfloat-abi=hard -mfpu=fpv4-sp-d16 -mthumb"
        CC  "-mcpu=cortex-m4 -mfloat-abi=hard -mfpu=fpv4-sp-d16 -mthumb -MMD -MP -DCPU_MKV31F512VLL12"
        CX  "-mcpu=cortex-m4 -mfloat-abi=hard -mfpu=fpv4-sp-d16 -mthumb -MMD -MP"
    )
endif()

if(CONFIG_MCUX_PRJSEG_twrkv46f150m_kboot_options)
    mcux_add_iar_configuration(
        AS  "--cpu=cortex-m4 --fpu=None"
        CC  "--cpu=cortex-m4 --fpu=None -DCPU_MKV46F256VLL16"
        CX  "--cpu=cortex-m4 --fpu=None"
    )
    mcux_add_mdk_configuration(
        AS  "-mcpu=cortex-m4"
        CC  "-mcpu=cortex-m4 -mfpu=fpv4-sp-d16 -DCPU_MKV46F256VLL16"
        CX  "-mcpu=cortex-m4 -mfpu=fpv4-sp-d16"
    )
    mcux_add_armgcc_configuration(
        AS  "-mcpu=cortex-m4 -mfloat-abi=hard -mfpu=fpv4-sp-d16 -mthumb"
        CC  "-mcpu=cortex-m4 -mfloat-abi=hard -mfpu=fpv4-sp-d16 -mthumb -MMD -MP -DCPU_MKV46F256VLL16"
        CX  "-mcpu=cortex-m4 -mfloat-abi=hard -mfpu=fpv4-sp-d16 -mthumb -MMD -MP"
    )
endif()

if(CONFIG_MCUX_PRJSEG_twrkv58f220m_kboot_options)
    mcux_add_iar_configuration(
        AS  "--cpu=cortex-m7 --fpu vfpv5_sp_d16"
        CC  "--cpu=cortex-m7 --fpu vfpv5_sp_d16 -DCPU_MKV58F1M0VLQ24 -DCPU_IS_ARM_CORTEX_M7=1"
        CX  "--cpu=cortex-m7 --fpu vfpv5_sp_d16"
    )
    mcux_add_mdk_configuration(
        AS  "-mcpu=cortex-m7"
        CC  "-mcpu=cortex-m7 -mfpu=fpv5-sp-d16 -DCPU_MKV58F1M0VLQ24 -DCPU_IS_ARM_CORTEX_M7=1"
        CX  "-mcpu=cortex-m7 -mfpu=fpv5-sp-d16"
    )
    mcux_add_armgcc_configuration(
        AS  "-mcpu=cortex-m7 -mfloat-abi=hard -mfpu=fpv5-sp-d16 -mthumb"
        CC  "-mcpu=cortex-m7 -mfloat-abi=hard -mfpu=fpv5-sp-d16 -mthumb -MMD -MP -DCPU_MKV58F1M0VLQ24 -DCPU_IS_ARM_CORTEX_M7=1"
        CX  "-mcpu=cortex-m7 -mfloat-abi=hard -mfpu=fpv5-sp-d16 -mthumb -MMD -MP"
    )
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.bootsources)
    mcux_component_version(2.7.0)
    mcux_add_source(
        SOURCES src/autobaud/autobaud.h
                src/autobaud/src/autobaud_irq.c
                src/bootloader/bl_peripheral_interface.h
                src/bootloader/bl_user_entry.h
                src/bootloader/bl_version.h
                src/bootloader/bootloader.h
                src/bootloader/bl_command.h
                src/bootloader/bl_context.h
                src/bootloader/bl_peripheral.h
                src/bootloader/bl_shutdown_cleanup.h
                src/bootloader/src/bl_user_entry.c
                src/bootloader/src/bl_main.c
                src/bootloader/src/bl_context.c
                src/bootloader/src/bl_exception_handler.c
                src/bootloader/src/bl_tree_root.c
                src/bootloader/src/bl_command.c
                src/bootloader/src/bl_shutdown_cleanup.c
                src/bootloader/bl_irq_common.h
                src/bootloader/bl_app_crc_check.h
                src/bootloader/src/bl_app_crc_check.c
                src/bootloader/src/bl_misc.c
                src/crc/crc16.h
                src/crc/crc32.h
                src/crc/src/crc16.c
                src/crc/src/crc32.c
                src/include/bootloader_common.h
                src/memory/memory.h
                src/memory/src/sram_init.h
                src/memory/src/memory.c
                src/memory/src/normal_memory.h
                src/memory/src/normal_memory.c
                src/memory/src/pattern_fill.h
                src/packet/command_packet.h
                src/packet/serial_packet.h
                src/packet/src/serial_packet.c
                src/property/property.h
                src/sbloader/sbloader.h
                src/sbloader/sb_file_format.h
                src/sbloader/src/sbloader.c
                src/utilities/fsl_rtos_abstraction.h
                src/utilities/fsl_assert.h
                src/utilities/vector_table_info.h
                src/utilities/src/fsl_assert.c
                src/utilities/src/fsl_rtos_abstraction.c
                src/utilities/src/debug_util.c
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES src/memory/src/pattern_fill.s
        TOOLCHAINS iar
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES src/memory/src/pattern_fill_gcc.S
        TOOLCHAINS mcux armgcc
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES src/memory/src/pattern_fill_mdk.s
        TOOLCHAINS mdk
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_include(
        INCLUDES src/autobaud
                 src/bootloader
                 src/crc
                 src/include
                 src/memory
                 src/memory/src
                 src/packet
                 src/property
                 src/sbloader
                 src/utilities
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.bootsources_kinetis)
    mcux_component_version(2.7.0)
    mcux_add_source(
        SOURCES src/drivers/smc/smc.c
                src/drivers/smc/smc.h
                src/memory/src/flash_memory.h
                src/memory/src/flash_memory.c
                src/property/src/property_kinetis.c
                src/utilities/kinetis_family.h
                src/bootloader/bl_reliable_update.h
                src/bootloader/src/bl_reliable_update.c
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_include(
        INCLUDES src/drivers/smc
                 src/memory/src
                 src/utilities
                 src/bootloader
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.bootsources_imxrt)
    mcux_component_version(2.7.0)
    mcux_add_source(
        SOURCES src/drivers/smc/smc.h
                src/drivers/dcp/bl_dcp.c
                src/drivers/dcp/bl_dcp.h
                src/drivers/trng/bl_trng.c
                src/drivers/trng/bl_trng.h
                src/bootloader/src/lpuart_peripheral_interface.c
                src/bootloader/src/usb_hid_msc_peripheral_interface.c
                src/bootloader/src/bl_nor_encrypt_bee.c
                src/bootloader/bl_nor_encrypt.h
                src/bootloader/src/bl_keyblob.c
                src/bootloader/bl_keyblob.h
                src/bootloader/src/bl_keyblob_dcp.c
                src/property/src/property_imx.c
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_include(
        INCLUDES src/drivers/smc
                 src/drivers/dcp
                 src/drivers/trng
                 src/bootloader
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.bootsources_lpc)
    mcux_component_version(2.7.0)
    mcux_add_source(
        SOURCES src/property/src/property_lpc.c
                src/drivers/smc/smc.h
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_include(
        INCLUDES src/drivers/smc
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.loadersources)
    mcux_component_version(2.7.0)
    mcux_add_source(
        SOURCES src/bootloader/flashloader_image.h
                src/bootloader/src/bl_flashloader.c
                src/bootloader/src/bl_exception_handler.c
                src/include/bootloader_common.h
                src/utilities/fsl_assert.h
                src/utilities/vector_table_info.h
                src/utilities/src/fsl_assert.c
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_include(
        INCLUDES src/bootloader
                 src/include
                 src/utilities
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.src_startup)
    mcux_component_version(2.7.0)
    mcux_add_source(
        SOURCES src/startup/startup.c
                src/include/bootloader_core.h
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_include(
        INCLUDES src/include
                 src/startup
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.postaction)
    mcux_component_version(2.7.0)
    mcux_add_source(
        SOURCES bin/elf.py
        TOOLCHAINS mcux
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES bin/create_fl_image_mcux.py
        TOOLCHAINS mcux
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
endif()

# if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.kinetis_files)
    # mcux_component_version(2.7.0)
    # mcux_add_source(
        # SOURCES apps/led_demo/src/*.c
                # apps/led_demo/src/*.bd
                # apps/led_demo/src/*.h
                # bin/Tools/mfgtools-rel/MfgTool2.exe
                # bin/Tools/mfgtools-rel/MfgToolLib.dll
                # bin/Tools/mfgtools-rel/UICfg.ini
                # bin/Tools/mfgtools-rel/cfg.ini
                # bin/Tools/mfgtools-rel/Profiles/Kinetis
                # Bootloader/player.ini
                # bin/Tools/mfgtools-rel/Profiles/Kinetis
                # Bootloader/OS
                # Firmware/*.xml
                # bin/Tools/mfgtools-rel/Profiles/Kinetis
                # Bootloader/OS
                # Firmware/files/simple.bd
                # bin/Tools/mfgtools-rel/Profiles/Kinetis
                # Bootloader/OS
                # Firmware/files/simple.hex
                # bin/Tools/mfgtools-rel/Profiles/Kinetis
                # Bootloader/OS
                # Firmware/files/simple.sb
                # bin/Tools/mfgtools-rel/Profiles/Kinetis
                # Bootloader/OS
                # Firmware/files/simple.srec
                # bin/Tools/mfgtools-rel/Profiles/Kinetis
                # Bootloader/OS
                # Firmware/files/Readme.txt
        # BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    # )
# endif()

# if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.imxrt_files)
    # mcux_component_version(2.7.0)
    # mcux_add_source(
        # SOURCES bin/Tools/mfgtools-rel/MfgTool2.exe
                # bin/Tools/mfgtools-rel/MfgToolLib.dll
                # bin/Tools/mfgtools-rel/UICfg.ini
        # BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    # )
# endif()

# if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.sdphost)
    # mcux_component_version(2.7.0)
    # mcux_add_source(
        # SOURCES bin/Tools/sdphost/linux/amd64/sdphost
                # bin/Tools/sdphost/linux/i386/sdphost
                # bin/Tools/sdphost/mac/sdphost
                # bin/Tools/sdphost/win/sdphost.exe
                # tools/tools/sdphost/gcc/Makefile
                # tools/tools/sdphost/mac-gcc/Makefile
                # tools/tools/sdphost/sdphost/*.cpp
                # tools/tools/sdphost/sdphost/*.h
                # tools/tools/sdphost/sdphost/sdphost.vcxproj
                # tools/tools/sdphost/sdphost/sdphost.vcxproj.filters
                # tools/tools/sdphost/sdphost/sdphost.vcxproj.user
                # tools/tools/sdphost/sdphost.sln
                # tools/tools/sdphost.xcodeproj/project.xcworkspace/contents.xcworkspacedata
                # tools/tools/sdphost.xcodeproj/project.pbxproj
        # BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    # )
# endif()

# if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.imxrt1050_files)
    # mcux_component_version(2.7.0)
    # mcux_add_source(
        # SOURCES bin/Tools/mfgtools-rel/Profiles/MXRT105X/OS
                # Firmware/ucl2.xml
                # bin/Tools/mfgtools-rel/Profiles/MXRT105X/OS
                # Firmware/*.bin
                # bin/Tools/mfgtools-rel/Profiles/MXRT105X/OS
                # Firmware/*.sb
                # bin/Tools/mfgtools-rel/cfg_MXRT105X.ini
                # bin/Tools/mfgtools-rel/README.txt
                # bin/Tools/bd_file/imxrt105x/*.bd
        # BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    # )
# endif()

# if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.imxrt106x_files)
    # mcux_component_version(2.7.0)
    # mcux_add_source(
        # SOURCES bin/Tools/mfgtools-rel/Profiles/MXRT106X/OS
                # Firmware/ucl2.xml
                # bin/Tools/mfgtools-rel/Profiles/MXRT106X/OS
                # Firmware/*.bin
                # bin/Tools/mfgtools-rel/Profiles/MXRT106X/OS
                # Firmware/*.sb
                # bin/Tools/mfgtools-rel/cfg_MXRT106X.ini
                # bin/Tools/mfgtools-rel/README.txt
                # bin/Tools/bd_file/imxrt106x/*.bd
        # BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    # )
# endif()

# if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.imxrt1020_files)
    # mcux_component_version(2.7.0)
    # mcux_add_source(
        # SOURCES bin/Tools/mfgtools-rel/Profiles/MXRT102X/OS
                # Firmware/ucl2.xml
                # bin/Tools/mfgtools-rel/Profiles/MXRT102X/OS
                # Firmware/*.bin
                # bin/Tools/mfgtools-rel/Profiles/MXRT102X/OS
                # Firmware/*.sb
                # bin/Tools/mfgtools-rel/cfg_MXRT102X.ini
                # bin/Tools/mfgtools-rel/README.txt
                # bin/Tools/bd_file/imxrt102x/*.bd
        # BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    # )
# endif()

# if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.imxrt1024_files)
    # mcux_component_version(2.7.0)
    # mcux_add_source(
        # SOURCES bin/Tools/mfgtools-rel/Profiles/MXRT1024/OS
                # Firmware/ucl2.xml
                # bin/Tools/mfgtools-rel/Profiles/MXRT1024/OS
                # Firmware/*.bin
                # bin/Tools/mfgtools-rel/Profiles/MXRT1024/OS
                # Firmware/*.sb
                # bin/Tools/mfgtools-rel/cfg_MXRT1024.ini
                # bin/Tools/mfgtools-rel/README.txt
                # bin/Tools/bd_file/imxrt1024/*.bd
        # BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    # )
# endif()

# if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.imxrt1015_files)
    # mcux_component_version(2.7.0)
    # mcux_add_source(
        # SOURCES bin/Tools/mfgtools-rel/Profiles/MXRT1015/OS
                # Firmware/ucl2.xml
                # bin/Tools/mfgtools-rel/Profiles/MXRT1015/OS
                # Firmware/*.bin
                # bin/Tools/mfgtools-rel/Profiles/MXRT1015/OS
                # Firmware/*.sb
                # bin/Tools/mfgtools-rel/cfg_MXRT1015.ini
                # bin/Tools/mfgtools-rel/README.txt
                # bin/Tools/bd_file/imxrt1015/*.bd
        # BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    # )
# endif()

# if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.imxrt1010_files)
    # mcux_component_version(2.7.0)
    # mcux_add_source(
        # SOURCES bin/Tools/mfgtools-rel/Profiles/MXRT101X/OS
                # Firmware/ucl2.xml
                # bin/Tools/mfgtools-rel/Profiles/MXRT101X/OS
                # Firmware/*.bin
                # bin/Tools/mfgtools-rel/Profiles/MXRT101X/OS
                # Firmware/*.sb
                # bin/Tools/mfgtools-rel/cfg_MXRT101X.ini
                # bin/Tools/bd_file/imxrt101x/*.bd
        # BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    # )
# endif()

# if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.imxrt1170_files)
    # mcux_component_version(2.7.0)
    # mcux_add_source(
        # SOURCES bin/Tools/mfgtools-rel/Profiles/MXRT117X/OS
                # Firmware/ucl2.xml
                # bin/Tools/mfgtools-rel/Profiles/MXRT117X/OS
                # Firmware/*.bin
                # bin/Tools/mfgtools-rel/Profiles/MXRT117X/OS
                # Firmware/*.sb
                # bin/Tools/mfgtools-rel/cfg_MXRT117X.ini
                # bin/Tools/mfgtools-rel/README.txt
                # bin/Tools/bd_file/imxrt117x/*.bd
        # BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    # )
# endif()

# if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.imxrt1160_files)
    # mcux_component_version(2.7.0)
    # mcux_add_source(
        # SOURCES bin/Tools/mfgtools-rel/Profiles/MXRT116X/OS
                # Firmware/ucl2.xml
                # bin/Tools/mfgtools-rel/Profiles/MXRT116X/OS
                # Firmware/*.bin
                # bin/Tools/mfgtools-rel/Profiles/MXRT116X/OS
                # Firmware/*.sb
                # bin/Tools/mfgtools-rel/cfg_MXRT116X.ini
                # bin/Tools/mfgtools-rel/README.txt
                # bin/Tools/bd_file/imxrt116x/*.bd
        # BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    # )
# endif()

# if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.qspi_demo_files)
    # mcux_component_version(2.7.0)
    # mcux_add_source(
        # SOURCES apps/demo_qspi/bdfile/program_keys.bd
                # apps/demo_qspi/bdfile/qspi_image_a000.bd
                # apps/demo_qspi/bdfile/qspi_image_alias_a000.bd
                # apps/demo_qspi/bdfile/qspi_image_encrypt_a000.bd
                # apps/demo_qspi/bdfile/key.txt
                # apps/QCBGenerator/binaries/*.bin
                # apps/QCBGenerator/build/codeblocks/QCBGenerator.cbp
                # apps/QCBGenerator/build/codeblocks/QCBGenerator.layout
                # apps/QCBGenerator/build/vs/QCBGenerator.sln
                # apps/QCBGenerator/build/vs/QCBGenerator.vcxproj
                # apps/QCBGenerator/build/vs/QCBGenerator.vcxproj.filters
                # apps/QCBGenerator/src/*.c
                # bin/Tools/QCBGenerator/win/QCBGenerator.exe
        # BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    # )
# endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.bootsources_MKE17Z9)
    mcux_component_version(2.7.0)
    mcux_add_source(
        SOURCES src/autobaud/autobaud.h
                src/autobaud/src/autobaud_irq.c
                src/bootloader/bl_peripheral_interface.h
                src/bootloader/bl_user_entry.h
                src/bootloader/bl_version.h
                src/bootloader/bootloader.h
                src/bootloader/bl_command.h
                src/bootloader/bl_context.h
                src/bootloader/bl_peripheral.h
                src/bootloader/bl_shutdown_cleanup.h
                src/bootloader/src/bl_user_entry.c
                src/bootloader/src/bl_main.c
                src/bootloader/src/bl_context.c
                src/bootloader/src/bl_exception_handler.c
                src/bootloader/src/bl_tree_root.c
                src/bootloader/src/bl_command_MKE17Z512.c
                src/bootloader/src/bl_shutdown_cleanup.c
                src/bootloader/bl_irq_common.h
                src/bootloader/bl_app_crc_check.h
                src/bootloader/src/bl_app_crc_check.c
                src/bootloader/src/bl_misc.c
                src/crc/crc16.h
                src/crc/crc32.h
                src/crc/src/crc16.c
                src/crc/src/crc32.c
                src/include/bootloader_common.h
                src/memory/memory.h
                src/memory/src/sram_init.h
                src/memory/src/memory.c
                src/memory/src/normal_memory.h
                src/memory/src/normal_memory.c
                src/startup/ar_asm_macros.h
                src/memory/src/pattern_fill.h
                src/packet/command_packet.h
                src/packet/serial_packet.h
                src/packet/src/serial_packet.c
                src/property/property.h
                src/sbloader/sbloader.h
                src/sbloader/sb_file_format.h
                src/sbloader/src/sbloader.c
                src/utilities/fsl_rtos_abstraction.h
                src/utilities/fsl_assert.h
                src/utilities/vector_table_info.h
                src/utilities/src/fsl_assert.c
                src/utilities/src/fsl_rtos_abstraction.c
                src/utilities/src/debug_util.c
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES src/memory/src/pattern_fill_gcc.S
        TOOLCHAINS mcux armgcc
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES src/memory/src/pattern_fill_mdk.s
        TOOLCHAINS mdk
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_include(
        INCLUDES src/autobaud
                 src/bootloader
                 src/crc
                 src/include
                 src/memory
                 src/memory/src
                 src/startup
                 src/packet
                 src/property
                 src/sbloader
                 src/utilities
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.bootsources_kinetis_MKE17Z9)
    mcux_component_version(2.7.0)
    mcux_add_source(
        SOURCES src/drivers/smc/smc.c
                src/drivers/smc/smc.h
                src/memory/src/flash_memory.h
                src/memory/src/flash_memory.c
                src/property/src/property_kinetis_MKE17Z512.c
                src/utilities/kinetis_family.h
                src/bootloader/bl_reliable_update.h
                src/bootloader/src/bl_reliable_update.c
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_include(
        INCLUDES src/drivers/smc
                 src/memory/src
                 src/utilities
                 src/bootloader
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.flashloader_loader_image)
    mcux_component_version(2.7.0)
    mcux_add_include(
        BASE_PATH ${SdkRootDirPath}
        TOOLCHAINS armgcc
        INCLUDES ./boards/${board}/bootloader_examples/flashloader/armgcc
    )
    mcux_add_include(
        BASE_PATH ${SdkRootDirPath} 
        TOOLCHAINS iar
        INCLUDES ./boards/${board}/bootloader_examples/flashloader/iar
    )
    mcux_add_include(
        BASE_PATH ${SdkRootDirPath} 
        TOOLCHAINS mdk
        INCLUDES ./boards/${board}/bootloader_examples/flashloader/mdk
    )
    # mcux_add_include(
        # BASE_PATH ${SdkRootDirPath} 
        # TOOLCHAINS mcux
        # INCLUDES .
    # )
  
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.CMSIS_cm7_headers)
    mcux_component_version(2.7.0)
    mcux_add_source(
        SOURCES mpu_armv7.h
        TOOLCHAINS mcux
        BASE_PATH ${SdkRootDirPath}/CMSIS/Core/Include/
    )
    mcux_add_source(
        SOURCES core_cm7.h
        TOOLCHAINS mcux
        BASE_PATH ${SdkRootDirPath}/CMSIS/Core/Include/
    )
    mcux_add_source(
        SOURCES cmsis_version.h
        TOOLCHAINS mcux
        BASE_PATH ${SdkRootDirPath}/CMSIS/Core/Include/
    )
    mcux_add_source(
        SOURCES cmsis_gcc.h
        TOOLCHAINS mcux
        BASE_PATH ${SdkRootDirPath}/CMSIS/Core/Include/
    )
    mcux_add_source(
        SOURCES cmsis_compiler.h
        TOOLCHAINS mcux
        BASE_PATH ${SdkRootDirPath}/CMSIS/Core/Include/
    )
    mcux_add_include(
        TOOLCHAINS mcux
        INCLUDES .
        BASE_PATH ${SdkRootDirPath}/CMSIS/Core/Include/
    )
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.src_bm_usb)
    mcux_component_version(2.7.0)
    mcux_add_source(
        SOURCES src/bm_usb/bootloader_hid_report_ids.h
                src/bm_usb/fat_directory_entry.h
                src/bm_usb/composite.h
                src/bm_usb/composite.c
                src/bm_usb/hid_bootloader.h
                src/bm_usb/hid_bootloader.c
                src/bm_usb/msc_disk.h
                src/bm_usb/msc_disk.c
                src/bm_usb/usb_descriptor.h
                src/bm_usb/usb_descriptor.c
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_include(
        INCLUDES src/bm_usb
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.usb.device.controller.driver)
    mcux_component_version(2.9.1)
    mcux_add_source(
        SOURCES device/usb_device_ehci.c
                device/usb_device_ehci.h
                device/usb_device.h
                device/usb_device_dci.c
                device/usb_device_dci.h
                ChangeLogKSDK.txt
        BASE_PATH ${SdkRootDirPath}/middleware/usb/
    )
    mcux_add_include(
        INCLUDES device
                 device
        BASE_PATH ${SdkRootDirPath}/middleware/usb/
    )
endif()
if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.usb.device.ip3511fs)
    mcux_component_version(2.7.0)
    mcux_add_include(
        INCLUDES device
        BASE_PATH ${SdkRootDirPath}/middleware/usb/
    )
    mcux_add_source(
        SOURCES device/usb_device_lpcip3511.c
                device/usb_device_lpcip3511.h
        BASE_PATH ${SdkRootDirPath}/middleware/usb/
    )
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.src_bm_usb_hid)
    mcux_component_version(2.7.0)
    mcux_add_source(
        SOURCES src/bm_usb/bootloader_hid_report_ids.h
                src/bm_usb/fat_directory_entry.h
                src/bm_usb/composite.h
                src/bm_usb/composite.c
                src/bm_usb/hid_bootloader.h
                src/bm_usb/hid_bootloader.c
                src/bm_usb/usb_descriptor.h
                src/bm_usb/usb_descriptor.c
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_include(
        INCLUDES src/bm_usb
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.usb.phy)
    mcux_component_version(2.7.0)
    mcux_add_source(
        SOURCES phy/usb_phy.c
                phy/usb_phy.h
        BASE_PATH ${SdkRootDirPath}/middleware/usb/
    )
    #mcux_add_include(
    #    INCLUDES phy
    #    BASE_PATH ${SdkRootDirPath}/middleware/usb/
    #)
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.usb.common_header)
    mcux_component_version(2.7.0)
    mcux_add_source(
        SOURCES include/usb.h
                include/usb_misc.h
                include/usb_spec.h
        BASE_PATH ${SdkRootDirPath}/middleware/usb/
    )
    mcux_add_include(
        INCLUDES include
        BASE_PATH ${SdkRootDirPath}/middleware/usb/
    )
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.usb.device.common_header)
    mcux_component_version(2.7.0)
    mcux_add_source(
        SOURCES device/usb_device.h
                device/usb_device_dci.h
        BASE_PATH ${SdkRootDirPath}/middleware/usb/
    )
    mcux_add_include(
        INCLUDES device
        BASE_PATH ${SdkRootDirPath}/middleware/usb/
    )
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.usb.device.stack)
    mcux_component_version(2.7.0)
    mcux_add_source(
        SOURCES device/class/usb_device_class.c
                device/class/usb_device_class.h
                device/usb_device_ch9.c
                device/usb_device_ch9.h
        BASE_PATH ${SdkRootDirPath}/middleware/usb/
    )
    mcux_add_include(
        INCLUDES device/class
                device
        BASE_PATH ${SdkRootDirPath}/middleware/usb/
    )
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.usb.device.hid)
    mcux_component_version(2.7.0)
    mcux_add_source(
        SOURCES device/class/usb_device_hid.c
                device/class/usb_device_hid.h
        BASE_PATH ${SdkRootDirPath}/middleware/usb/
    )
    mcux_add_include(
        INCLUDES device/class
                device
        BASE_PATH ${SdkRootDirPath}/middleware/usb/
    )
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.usb.device.khci)
    mcux_component_version(2.7.0)
    mcux_add_source(
        SOURCES device/usb_device_khci.c
                device/usb_device_khci.h
        BASE_PATH ${SdkRootDirPath}/middleware/usb/
    )
    mcux_add_include(
        INCLUDES device
        BASE_PATH ${SdkRootDirPath}/middleware/usb/
    )
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.usb.device.msd)
    mcux_component_version(2.7.0)
    mcux_add_source(
        SOURCES device/class/usb_device_msc.c
                device/class/usb_device_msc.h
                device/class/usb_device_msc_ufi.c
                device/class/usb_device_msc_ufi.h
        BASE_PATH ${SdkRootDirPath}/middleware/usb/
    )
    mcux_add_include(
        INCLUDES device/class
        BASE_PATH ${SdkRootDirPath}/middleware/usb/
    )
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.usb.device.stack)
    mcux_component_version(2.7.0)
    mcux_add_source(
        SOURCES device/usb_device_ch9.c device/usb_device_ch9.h
                device/class/usb_device_class.c device/class/usb_device_class.h
        BASE_PATH ${SdkRootDirPath}/middleware/usb/
    )
    mcux_add_include(
        INCLUDES device device/class
        BASE_PATH ${SdkRootDirPath}/middleware/usb/
    )
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.src_security)
    mcux_component_version(2.7.0)
    mcux_add_source(
        SOURCES src/security/aes_security.h
                src/security/aes128_key_wrap_unwrap.h
                src/security/cbc_mac.h
                src/security/src/aes_security.c
                src/security/src/aes128_key_wrap_unwrap.c
                src/security/src/cbc_mac.c
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_include(
        INCLUDES src/security
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.qspi_led_demo)
    mcux_component_version(2.7.0)
    mcux_add_source(
        SOURCES apps/demo_qspi/led_demo/src/led_demo.c
                apps/demo_qspi/led_demo/src/led_bsp.h
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_include(
        INCLUDES apps/demo_qspi/led_demo/src
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.qspi_led_demo_qspi)
    mcux_component_version(2.7.0)
    mcux_add_source(
        SOURCES apps/demo_qspi/led_demo/src/led_demo_qspi.c
                apps/demo_qspi/led_demo/src/led_bsp.h
                apps/demo_qspi/led_demo/src/misc.c
                apps/demo_qspi/led_demo/src/misc.h
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_include(
        INCLUDES apps/demo_qspi/led_demo/src
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.drv_ocotp)
    mcux_component_version(2.7.0)
    mcux_add_source(
        SOURCES src/drivers/ocotp/bl_ocotp.c
                src/drivers/ocotp/bl_ocotp.h
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_include(
        INCLUDES src/drivers/ocotp
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.drv_serial_nor_eeprom)
    mcux_component_version(2.7.0)
    mcux_add_source(
        SOURCES src/drivers/serial_nor_eeprom/serial_nor_eeprom.c
                src/drivers/serial_nor_eeprom/serial_nor_eeprom.h
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_include(
        INCLUDES src/drivers/serial_nor_eeprom
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.mem_spi_nor_eeprom)
    mcux_component_version(2.7.0)
    mcux_add_source(
        SOURCES src/memory/src/spi_nor_eeprom_memory.c
                src/memory/src/spi_nor_eeprom_memory.h
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_include(
        INCLUDES src/memory/src
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.drv_sdmmc)
    mcux_component_version(2.7.0)
    mcux_add_source(
        SOURCES src/drivers/usdhc/bl_usdhc.c
                src/drivers/usdhc/bl_usdhc.h
                src/drivers/sdmmc/src/fsl_mmc.c
                src/drivers/sdmmc/inc/fsl_mmc.h
                src/drivers/sdmmc/src/fsl_sd.c
                src/drivers/sdmmc/inc/fsl_sd.h
                src/drivers/sdmmc/src/fsl_sdmmc_common.c
                src/drivers/sdmmc/inc/fsl_sdmmc_common.h
                src/drivers/sdmmc/inc/fsl_sdmmc_host.h
                src/drivers/sdmmc/port/usdhc/polling/fsl_sdmmc_host.c
                src/drivers/sdmmc/inc/fsl_sdmmc_spec.h
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_include(
        INCLUDES src/drivers/usdhc
                 src/drivers/sdmmc/inc
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.mem_sdmmc)
    mcux_component_version(2.7.0)
    mcux_add_source(
        SOURCES src/memory/src/sd_memory.c
                src/memory/src/sd_memory.h
                src/memory/src/mmc_memory.c
                src/memory/src/mmc_memory.h
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_include(
        INCLUDES src/memory/src
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.drv_semc_nor)
    mcux_component_version(2.7.0)
    mcux_add_source(
        SOURCES src/drivers/semc/bl_semc.c
                src/drivers/semc/bl_semc.h
                src/drivers/semc_nor/semc_nor_flash.c
                src/drivers/semc_nor/semc_nor_flash.h
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_include(
        INCLUDES src/drivers/semc
                 src/drivers/semc_nor
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.mem_semc_nor)
    mcux_component_version(2.7.0)
    mcux_add_source(
        SOURCES src/memory/src/semc_nor_memory.c
                src/memory/src/semc_nor_memory.h
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_include(
        INCLUDES src/memory/src
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.drv_semc_nand)
    mcux_component_version(2.7.0)
    mcux_add_source(
        SOURCES src/drivers/semc/bl_semc.c
                src/drivers/semc/bl_semc.h
                src/drivers/semc_nand/semc_nand_flash.c
                src/drivers/semc_nand/semc_nand_flash.h
                src/drivers/nand_ecc/nand_ecc.c
                src/drivers/nand_ecc/nand_ecc.h
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_include(
        INCLUDES src/drivers/semc
                 src/drivers/semc_nand
                 src/drivers/nand_ecc
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.mem_semc_nand)
    mcux_component_version(2.7.0)
    mcux_add_source(
        SOURCES src/memory/src/semc_nand_memory.c
                src/memory/src/semc_nand_memory.h
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_include(
        INCLUDES src/memory/src
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.drv_flexspi_nor)
    mcux_component_version(2.7.0)
    mcux_add_source(
        SOURCES src/drivers/flexspi/bl_flexspi.c
                src/drivers/flexspi/bl_flexspi.h
                src/drivers/flexspi_nor/flexspi_nor_flash.c
                src/drivers/flexspi_nor/flexspi_nor_flash.h
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_include(
        INCLUDES src/drivers/flexspi
                 src/drivers/flexspi_nor
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.mem_flexspi_nor)
    mcux_component_version(2.7.0)
    mcux_add_source(
        SOURCES src/memory/src/flexspi_nor_memory.c
                src/memory/src/flexspi_nor_memory.h
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_include(
        INCLUDES src/memory/src
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.drv_flexspi_nand)
    mcux_component_version(2.7.0)
    mcux_add_source(
        SOURCES src/drivers/flexspi/bl_flexspi.c
                src/drivers/flexspi/bl_flexspi.h
                src/drivers/flexspi_nand/flexspi_nand_flash.c
                src/drivers/flexspi_nand/flexspi_nand_flash.h
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_include(
        INCLUDES src/drivers/flexspi
                 src/drivers/flexspi_nand
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.mem_spi_nand)
    mcux_component_version(2.7.0)
    mcux_add_source(
        SOURCES src/memory/src/spinand_memory.c
                src/memory/src/spinand_memory.h
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_include(
        INCLUDES src/memory/src
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.drv_spifi)
    mcux_component_version(2.7.0)
    mcux_add_source(
        SOURCES src/drivers/spifi/bl_spifi.c
                src/drivers/spifi/bl_spifi.h
                src/drivers/spifi_nor/spifi_nor_flash.c
                src/drivers/spifi_nor/spifi_nor_flash.h
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_include(
        INCLUDES src/drivers/spifi
                 src/drivers/spifi_nor
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.interface_otp)
    mcux_component_version(2.7.0)
    mcux_add_source(
        SOURCES src/drivers/otp/otp.c
                src/drivers/otp/otp.h
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_include(
        INCLUDES src/drivers/otp
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.interface_aes_otp)
    mcux_component_version(2.7.0)
    mcux_add_source(
        SOURCES src/drivers/aes_otp/aes_otp.c
                src/drivers/aes_otp/aes_otp.h
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_include(
        INCLUDES src/drivers/aes_otp
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.drv_microseconds)
    mcux_component_version(2.7.0)
    mcux_add_source(
        SOURCES src/drivers/microseconds/microseconds.h
                src/drivers/microseconds/src/microseconds_sysclk.c
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_include(
        INCLUDES src/drivers/microseconds
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.drv_microseconds_pit)
    mcux_component_version(2.7.0)
    mcux_add_source(
        SOURCES src/drivers/microseconds/microseconds.h
                src/drivers/microseconds/src/microseconds_pit.c
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_include(
        INCLUDES src/drivers/microseconds
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.drv_microseconds_lpit)
    mcux_component_version(2.7.0)
    mcux_add_source(
        SOURCES src/drivers/microseconds/microseconds.h
                src/drivers/microseconds/src/microseconds_lpit.c
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_include(
        INCLUDES src/drivers/microseconds
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.drv_qspi)
    mcux_component_version(2.7.0)
    mcux_add_source(
        SOURCES src/drivers/qspi/qspi.h
                src/drivers/qspi/src/qspi.c
                src/memory/src/qspi_memory.c
                src/memory/src/qspi_memory.h
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_include(
        INCLUDES src/drivers/qspi
                 src/memory/src
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.drv_mmcau)
    mcux_component_version(2.7.0)
    mcux_add_source(
        SOURCES src/drivers/mmcau/mmcau.h
                src/drivers/mmcau/src/mmcau_aes_functions.c
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_include(
        INCLUDES src/drivers/mmcau
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.drv_ltc)
    mcux_component_version(2.7.0)
    mcux_add_source(
        SOURCES src/drivers/ltc/ltc.h
                src/drivers/ltc/src/ltc_aes_functions.c
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_include(
        INCLUDES src/drivers/ltc
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.qspi_milliseconds)
    mcux_component_version(2.7.0)
    mcux_add_source(
        SOURCES apps/demo_qspi/led_demo/src/milliseconds_delay.h
                apps/demo_qspi/led_demo/src/milliseconds_delay.c
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_include(
        INCLUDES apps/demo_qspi/led_demo/src
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.milliseconds)
    mcux_component_version(2.7.0)
    mcux_add_source(
        SOURCES apps/led_demo/src/milliseconds_delay.h
                apps/led_demo/src/milliseconds_delay.c
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_include(
        INCLUDES apps/led_demo/src
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.drv_otfad)
    mcux_component_version(2.7.0)
    mcux_add_source(
        SOURCES src/drivers/otfad/fsl_otfad_driver.h
                src/drivers/otfad/src/fsl_otfad_driver.c
                src/drivers/otfad/hal/fsl_otfad_hal.c
                src/drivers/otfad/hal/fsl_otfad_hal.h
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_include(
        INCLUDES src/drivers/otfad
                 src/drivers/otfad/hal
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.drv_edgelock)
    mcux_component_version(2.7.0)
    mcux_add_source(
        SOURCES src/drivers/edgelock/fsl_edgelock.c
                src/drivers/edgelock/fsl_edgelock.h
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_include(
        INCLUDES src/drivers/edgelock
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.MK22F51212_startup)
    mcux_component_version(2.7.0)
    mcux_add_source(
        SOURCES ../../devices/Kinetis/K/MK22F51212/system_MK22F51212.h
                ../../devices/Kinetis/K/MK22F51212/system_MK22F51212.c
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES src/startup/crt0.s
        TOOLCHAINS iar
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES src/startup/crt0_gcc.S
        TOOLCHAINS mcux armgcc
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES targets/MK22F51212/src/startup/iar/startup_MK22F51212.s
        TOOLCHAINS iar
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES targets/MK22F51212/src/startup/gcc/startup_MK22F51212.S
        TOOLCHAINS mcux armgcc
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES targets/MK22F51212/src/startup/arm/startup_MK22F51212.S
        TOOLCHAINS mdk
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_include(
        INCLUDES ../../devices/MK22F51212
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.MK22F51212_sources)
    mcux_component_version(2.7.0)
    mcux_add_source(
        SOURCES targets/MK22F51212/src/bootloader_config.h
                targets/MK22F51212/src/bl_clock_config_MK22F51212.c
                targets/MK22F51212/src/hardware_init_MK22F51212.c
                targets/MK22F51212/src/memory_map_MK22F51212.c
                targets/MK22F51212/src/bl_peripherals_MK22F51212.c
                targets/MK22F51212/src/peripherals_pinmux.h
                targets/MK22F51212/src/target_config.h
                targets/MK22F51212/src/usb_device_config.h
                targets/common/src/pinmux_utility_common.c
                targets/common/src/bl_dspi_irq_config_common.c
                targets/common/src/bl_i2c_irq_config_common.c
                targets/common/src/bl_uart_irq_config_common.c
                src/bootloader/src/scuart_peripheral_interface.c
                src/bootloader/src/dspi_peripheral_interface.c
                src/bootloader/src/i2c_peripheral_interface.c
                src/bootloader/src/usb_hid_msc_peripheral_interface.c
                src/memory/src/sram_init_cm4.c
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_include(
        INCLUDES targets/MK22F51212/src
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.MK64F12_startup)
    mcux_component_version(2.7.0)
    mcux_add_source(
        SOURCES ../../devices/MK64F12/system_MK64F12.h
                ../../devices/MK64F12/system_MK64F12.c
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES src/startup/crt0.s
        TOOLCHAINS iar
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES src/startup/crt0_gcc.S
        TOOLCHAINS mcux armgcc
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES targets/MK64F12/src/startup/iar/startup_MK64F12.s
        TOOLCHAINS iar
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES targets/MK64F12/src/startup/gcc/startup_MK64F12.S
        TOOLCHAINS mcux armgcc
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES targets/MK64F12/src/startup/arm/startup_MK64F12.S
        TOOLCHAINS mdk
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_include(
        INCLUDES ../../devices/MK64F12
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.MK64F12_sources)
    mcux_component_version(2.7.0)
    mcux_add_source(
        SOURCES targets/MK64F12/src/bootloader_config.h
                targets/MK64F12/src/bl_clock_config_MK64F12.c
                targets/MK64F12/src/hardware_init_MK64F12.c
                targets/MK64F12/src/memory_map_MK64F12.c
                targets/MK64F12/src/bl_peripherals_MK64F12.c
                targets/MK64F12/src/peripherals_pinmux.h
                targets/MK64F12/src/target_config.h
                targets/MK64F12/src/usb_device_config.h
                targets/common/src/pinmux_utility_common.c
                targets/common/src/bl_dspi_irq_config_common.c
                targets/common/src/bl_i2c_irq_config_common.c
                targets/common/src/bl_uart_irq_config_common.c
                src/bootloader/src/scuart_peripheral_interface.c
                src/bootloader/src/dspi_peripheral_interface.c
                src/bootloader/src/i2c_peripheral_interface.c
                src/bootloader/src/usb_hid_msc_peripheral_interface.c
                src/memory/src/sram_init_cm4.c
                src/drivers/ltc/ltc.h
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_include(
        INCLUDES targets/MK64F12/src
                 src/drivers/ltc
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.MK80F25615_startup)
    mcux_component_version(2.7.0)
    mcux_add_source(
        SOURCES ../../devices/MK80F25615/system_MK80F25615.h
                ../../devices/MK80F25615/system_MK80F25615.c
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES src/startup/crt0.s
        TOOLCHAINS iar
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES src/startup/crt0_gcc.S
        TOOLCHAINS mcux armgcc
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES targets/MK80F25615/src/startup/iar/startup_MK80F25615.s
        TOOLCHAINS iar
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES targets/MK80F25615/src/startup/gcc/startup_MK80F25615.S
        TOOLCHAINS mcux armgcc
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES targets/MK80F25615/src/startup/arm/startup_MK80F25615.S
        TOOLCHAINS mdk
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_include(
        INCLUDES ../../devices/MK80F25615
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.MK80F25615_sources)
    mcux_component_version(2.7.0)
    mcux_add_source(
        SOURCES targets/MK80F25615/src/bootloader_config.h
                targets/MK80F25615/src/bl_clock_config_MK80F25615.c
                targets/MK80F25615/src/hardware_init_MK80F25615.c
                targets/MK80F25615/src/memory_map_MK80F25615.c
                targets/MK80F25615/src/external_memory_property_map_MK80F25615.c
                targets/MK80F25615/src/bl_peripherals_MK80F25615.c
                targets/MK80F25615/src/peripherals_pinmux.h
                targets/MK80F25615/src/target_config.h
                targets/MK80F25615/src/usb_device_config.h
                targets/common/src/pinmux_utility_common.c
                targets/common/src/bl_dspi_irq_config_common.c
                targets/common/src/bl_i2c_irq_config_common.c
                targets/common/src/bl_lpuart_irq_config_common.c
                src/bootloader/src/lpuart_peripheral_interface.c
                src/bootloader/src/dspi_peripheral_interface.c
                src/bootloader/src/i2c_peripheral_interface.c
                src/bootloader/src/usb_hid_msc_peripheral_interface.c
                src/memory/src/sram_init_cm4.c
                src/drivers/ltc/ltc.h
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_include(
        INCLUDES targets/MK80F25615/src
                 src/drivers/ltc
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.MK80F25615_qspi_demo_startup)
    mcux_component_version(2.7.0)
    mcux_add_source(
        SOURCES apps/demo_qspi/led_demo/devices/MK80F25615/startup/system_MK80F25615.h
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES src/startup/crt0_gcc.S
        TOOLCHAINS mcux armgcc
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_include(
        INCLUDES apps/demo_qspi/led_demo/devices/MK80F25615/startup
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.MK80F25615_qspi_pflash_startup)
    mcux_component_version(2.7.0)
    mcux_add_source(
        SOURCES apps/demo_qspi/led_demo/devices/MK80F25615/startup/system_MK80F25615.c
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES apps/demo_qspi/led_demo/devices/MK80F25615/startup/iar/startup_MK80F25615.s
        TOOLCHAINS iar
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES apps/demo_qspi/led_demo/devices/MK80F25615/startup/arm/startup_MK80F25615.S
        TOOLCHAINS mdk
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES apps/demo_qspi/led_demo/devices/MK80F25615/startup/gcc/startup_MK80F25615.S
        TOOLCHAINS mcux armgcc
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.MK80F25615_qspi_startup)
    mcux_component_version(2.7.0)
    mcux_add_source(
        SOURCES apps/demo_qspi/led_demo/devices/MK80F25615/startup/system_MK80F25615_qspi.c
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES apps/demo_qspi/led_demo/devices/MK80F25615/startup/iar/startup_MK80F25615_qspi.s
        TOOLCHAINS iar
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES apps/demo_qspi/led_demo/devices/MK80F25615/startup/arm/startup_MK80F25615_qspi.S
        TOOLCHAINS mdk
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES apps/demo_qspi/led_demo/devices/MK80F25615/startup/gcc/startup_MK80F25615_qspi.S
        TOOLCHAINS mcux armgcc
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.MK82F25615_startup)
    mcux_component_version(2.7.0)
    mcux_add_source(
        SOURCES ../../devices/MK82F25615/system_MK82F25615.h
                ../../devices/MK82F25615/system_MK82F25615.c
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES src/startup/crt0.s
        TOOLCHAINS iar
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES src/startup/crt0_gcc.S
        TOOLCHAINS mcux armgcc
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES targets/MK82F25615/src/startup/iar/startup_MK82F25615.s
        TOOLCHAINS iar
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES targets/MK82F25615/src/startup/gcc/startup_MK82F25615.S
        TOOLCHAINS mcux armgcc
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES targets/MK82F25615/src/startup/arm/startup_MK82F25615.S
        TOOLCHAINS mdk
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_include(
        INCLUDES ../../devices/MK82F25615
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.MK82F25615_sources)
    mcux_component_version(2.7.0)
    mcux_add_source(
        SOURCES targets/MK82F25615/src/bootloader_config.h
                targets/MK82F25615/src/bl_clock_config_MK82F25615.c
                targets/MK82F25615/src/hardware_init_MK82F25615.c
                targets/MK82F25615/src/memory_map_MK82F25615.c
                targets/MK82F25615/src/external_memory_property_map_MK82F25615.c
                targets/MK82F25615/src/bl_peripherals_MK82F25615.c
                targets/MK82F25615/src/peripherals_pinmux.h
                targets/MK82F25615/src/target_config.h
                targets/MK82F25615/src/usb_device_config.h
                targets/common/src/pinmux_utility_common.c
                targets/common/src/bl_dspi_irq_config_common.c
                targets/common/src/bl_i2c_irq_config_common.c
                targets/common/src/bl_lpuart_irq_config_common.c
                src/bootloader/src/lpuart_peripheral_interface.c
                src/bootloader/src/dspi_peripheral_interface.c
                src/bootloader/src/i2c_peripheral_interface.c
                src/bootloader/src/usb_hid_msc_peripheral_interface.c
                src/memory/src/sram_init_cm4.c
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_include(
        INCLUDES targets/MK82F25615/src
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.MK82F25615_qspi_demo_startup)
    mcux_component_version(2.7.0)
    mcux_add_source(
        SOURCES apps/demo_qspi/led_demo/devices/MK82F25615/startup/system_MK82F25615.h
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES src/startup/crt0_gcc.S
        TOOLCHAINS mcux armgcc
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_include(
        INCLUDES apps/demo_qspi/led_demo/devices/MK82F25615/startup
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.MK82F25615_qspi_pflash_startup)
    mcux_component_version(2.7.0)
    mcux_add_source(
        SOURCES apps/demo_qspi/led_demo/devices/MK82F25615/startup/system_MK82F25615.c
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES apps/demo_qspi/led_demo/devices/MK82F25615/startup/iar/startup_MK82F25615.s
        TOOLCHAINS iar
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES apps/demo_qspi/led_demo/devices/MK82F25615/startup/arm/startup_MK82F25615.S
        TOOLCHAINS mdk
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES apps/demo_qspi/led_demo/devices/MK82F25615/startup/gcc/startup_MK82F25615.S
        TOOLCHAINS mcux armgcc
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.MK82F25615_qspi_startup)
    mcux_component_version(2.7.0)
    mcux_add_source(
        SOURCES apps/demo_qspi/led_demo/devices/MK82F25615/startup/system_MK82F25615_qspi.c
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES apps/demo_qspi/led_demo/devices/MK82F25615/startup/iar/startup_MK82F25615_qspi.s
        TOOLCHAINS iar
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES apps/demo_qspi/led_demo/devices/MK82F25615/startup/arm/startup_MK82F25615_qspi.S
        TOOLCHAINS mdk
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES apps/demo_qspi/led_demo/devices/MK82F25615/startup/gcc/startup_MK82F25615_qspi.S
        TOOLCHAINS mcux armgcc
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.MKV58F24_startup)
    mcux_component_version(2.7.0)
    mcux_add_source(
        SOURCES ../../devices/MKV58F24/system_MKV58F24.h
                ../../devices/MKV58F24/system_MKV58F24.c
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES src/startup/crt0.s
        TOOLCHAINS iar
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES src/startup/crt0_gcc.S
        TOOLCHAINS mcux armgcc
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES targets/MKV58F24/src/startup/iar/startup_MKV58F24.s
        TOOLCHAINS iar
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES targets/MKV58F24/src/startup/gcc/startup_MKV58F24.S
        TOOLCHAINS mcux armgcc
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES targets/MKV58F24/src/startup/arm/startup_MKV58F24.S
        TOOLCHAINS mdk
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_include(
        INCLUDES ../../devices/MKV58F24
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.MKV58F24_sources)
    mcux_component_version(2.7.0)
    mcux_add_source(
        SOURCES targets/MKV58F24/src/bootloader_config.h
                targets/MKV58F24/src/bl_clock_config_MKV58F24.c
                targets/MKV58F24/src/hardware_init_MKV58F24.c
                targets/MKV58F24/src/memory_map_MKV58F24.c
                targets/MKV58F24/src/bl_peripherals_MKV58F24.c
                targets/MKV58F24/src/peripherals_pinmux.h
                targets/MKV58F24/src/target_config.h
                targets/common/src/pinmux_utility_common.c
                targets/common/src/bl_dspi_irq_config_common.c
                targets/common/src/bl_i2c_irq_config_common.c
                targets/common/src/bl_uart_irq_config_common.c
                src/bootloader/src/scuart_peripheral_interface.c
                src/bootloader/src/dspi_peripheral_interface.c
                src/bootloader/src/i2c_peripheral_interface.c
                src/bootloader/src/flexcan_peripheral_interface.c
                src/memory/src/sram_init_cm7.c
                src/drivers/ltc/ltc.h
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_include(
        INCLUDES targets/MKV58F24/src
                 src/drivers/ltc
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.K32L2A41A_startup)
    mcux_component_version(2.7.0)
    mcux_add_source(
        SOURCES ../../devices/Kinetis/K32L/K32L2A41A/system_K32L2A41A.h
                ../../devices/Kinetis/K32L/K32L2A41A/system_K32L2A41A.c
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES src/startup/crt0.s
        TOOLCHAINS iar
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES targets/K32L2A41A/src/startup/iar/startup_K32L2A41A.s
        TOOLCHAINS iar
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES targets/K32L2A41A/src/startup/gcc/startup_K32L2A41A.S
        TOOLCHAINS mcux armgcc
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES targets/K32L2A41A/src/startup/arm/startup_K32L2A41A.S
        TOOLCHAINS mdk
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_include(
        INCLUDES ../../devices/K32L2A41A
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.K32L2A41A_sources)
    mcux_component_version(2.7.0)
    mcux_add_source(
        SOURCES targets/K32L2A41A/src/bootloader_config.h
                targets/K32L2A41A/src/bl_clock_config_K32L2A41A.c
                targets/K32L2A41A/src/hardware_init_K32L2A41A.c
                targets/K32L2A41A/src/memory_map_K32L2A41A.c
                targets/K32L2A41A/src/bl_peripherals_K32L2A41A.c
                targets/K32L2A41A/src/peripherals_pinmux.h
                targets/K32L2A41A/src/target_config.h
                targets/K32L2A41A/src/usb_device_config.h
                targets/K32L2A41A/src/bl_lpspi_irq_config_K32L2A41A.c
                targets/K32L2A41A/src/bl_lpi2c_irq_config_K32L2A41A.c
                targets/K32L2A41A/src/bl_lpuart_irq_config_K32L2A41A.c
                targets/common/src/pinmux_utility_common.c
                targets/common/src/bl_intmux_irq.c
                src/bootloader/src/lpuart_peripheral_interface.c
                src/bootloader/src/lpspi_peripheral_interface.c
                src/bootloader/src/lpi2c_peripheral_interface.c
                src/bootloader/src/usb_hid_msc_peripheral_interface.c
                src/memory/src/sram_init_cm0plus.c
                src/drivers/ltc/ltc.h
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_include(
        INCLUDES targets/K32L2A41A/src
                 src/drivers/ltc
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.MKM35Z7_startup)
    mcux_component_version(2.7.0)
    mcux_add_source(
        SOURCES ../../devices/Kinetis/KM/MKM35Z7/system_MKM35Z7.h
                ../../devices/Kinetis/KM/MKM35Z7/system_MKM35Z7.c
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES src/startup/crt0.s
        TOOLCHAINS iar
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES targets/MKM35Z7/src/startup/iar/startup_MKM35Z7.s
        TOOLCHAINS iar
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES targets/MKM35Z7/src/startup/gcc/startup_MKM35Z7.S
        TOOLCHAINS mcux armgcc
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES targets/MKM35Z7/src/startup/arm/startup_MKM35Z7.S
        TOOLCHAINS mdk
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_include(
        INCLUDES ../../devices/MKM35Z7
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.MKM35Z7_sources)
    mcux_component_version(2.7.0)
    mcux_add_source(
        SOURCES targets/MKM35Z7/src/bootloader_config.h
                targets/MKM35Z7/src/bl_clock_config_MKM35Z7.c
                targets/MKM35Z7/src/hardware_init_MKM35Z7.c
                targets/MKM35Z7/src/memory_map_MKM35Z7.c
                targets/MKM35Z7/src/bl_peripherals_MKM35Z7.c
                targets/MKM35Z7/src/peripherals_pinmux.h
                targets/MKM35Z7/src/target_config.h
                targets/common/src/pinmux_utility_common.c
                targets/common/src/bl_i2c_irq_config_common.c
                targets/common/src/bl_uart_irq_config_common.c
                src/bootloader/src/uart_peripheral_interface.c
                src/bootloader/src/spi_peripheral_interface.c
                src/bootloader/src/i2c_peripheral_interface.c
                src/memory/src/sram_init_cm0plus.c
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_include(
        INCLUDES targets/MKM35Z7/src
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.MKE16Z4_startup)
    mcux_component_version(2.7.0)
    mcux_add_source(
        SOURCES ../../devices/Kinetis/KE/MKE16Z4/system_MKE16Z4.h
                ../../devices/Kinetis/KE/MKE16Z4/system_MKE16Z4.c
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES src/startup/crt0.s
        TOOLCHAINS iar
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES targets/MKE16Z4/src/startup/iar/startup_MKE16Z4.s
        TOOLCHAINS iar
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES targets/MKE16Z4/src/startup/gcc/startup_MKE16Z4.S
        TOOLCHAINS mcux armgcc
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES targets/MKE16Z4/src/startup/arm/startup_MKE16Z4.S
        TOOLCHAINS mdk
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_include(
        INCLUDES ../../devices/MKE16Z4
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.MKE16Z4_sources)
    mcux_component_version(2.7.0)
    mcux_add_source(
        SOURCES targets/MKE16Z4/src/bootloader_config.h
                targets/MKE16Z4/src/bl_clock_config_MKE16Z4.c
                targets/MKE16Z4/src/hardware_init_MKE16Z4.c
                targets/MKE16Z4/src/memory_map_MKE16Z4.c
                targets/MKE16Z4/src/bl_peripherals_MKE16Z4.c
                targets/MKE16Z4/src/peripherals_pinmux.h
                targets/MKE16Z4/src/target_config.h
                targets/common/src/pinmux_utility_common.c
                targets/common/src/bl_lpi2c_irq_config_common.c
                targets/common/src/bl_lpuart_irq_config_common.c
                targets/common/src/bl_lpspi_irq_config_common.c
                src/bootloader/src/lpuart_peripheral_interface.c
                src/bootloader/src/lpspi_peripheral_interface.c
                src/bootloader/src/lpi2c_peripheral_interface.c
                src/bootloader/src/mscan_peripheral_interface.c
                src/memory/src/sram_init_cm0plus.c
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_include(
        INCLUDES targets/MKE16Z4/src
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.MKE17Z7_startup)
    mcux_component_version(2.7.0)
    mcux_add_source(
        SOURCES ../../devices/Kinetis/KE/MKE17Z7/system_MKE17Z7.h
                ../../devices/Kinetis/KE/MKE17Z7/system_MKE17Z7.c
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES src/startup/crt0.s
        TOOLCHAINS iar
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES targets/MKE17Z7/src/startup/iar/startup_MKE17Z7.s
        TOOLCHAINS iar
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES targets/MKE17Z7/src/startup/gcc/startup_MKE17Z7.S
        TOOLCHAINS mcux armgcc
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES targets/MKE17Z7/src/startup/arm/startup_MKE17Z7.S
        TOOLCHAINS mdk
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_include(
        INCLUDES ../../devices/MKE17Z7
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.MKE17Z7_sources)
    mcux_component_version(2.7.0)
    mcux_add_source(
        SOURCES targets/MKE17Z7/src/bootloader_config.h
                targets/MKE17Z7/src/bl_clock_config_MKE17Z7.c
                targets/MKE17Z7/src/hardware_init_MKE17Z7.c
                targets/MKE17Z7/src/memory_map_MKE17Z7.c
                targets/MKE17Z7/src/bl_peripherals_MKE17Z7.c
                targets/MKE17Z7/src/peripherals_pinmux.h
                targets/MKE17Z7/src/target_config.h
                targets/common/src/pinmux_utility_common.c
                targets/common/src/bl_lpi2c_irq_config_common.c
                targets/common/src/bl_lpuart_irq_config_common.c
                targets/common/src/bl_lpspi_irq_config_common.c
                src/bootloader/src/lpuart_peripheral_interface.c
                src/bootloader/src/lpspi_peripheral_interface.c
                src/bootloader/src/lpi2c_peripheral_interface.c
                src/memory/src/sram_init_cm0plus.c
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_include(
        INCLUDES targets/MKE17Z7/src
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.MKE17Z9_startup)
    mcux_component_version(2.7.0)
    mcux_add_source(
        SOURCES ../../devices/Kinetis/KE/MKE17Z9/system_MKE17Z9.h
                targets/MKE17Z9/src/startup/system_MKE17Z9.c
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES src/startup/crt0.s
        TOOLCHAINS iar
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES targets/MKE17Z9/src/startup/iar/startup_MKE17Z9.s
        TOOLCHAINS iar
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES targets/MKE17Z9/src/startup/gcc/startup_MKE17Z9.S
        TOOLCHAINS mcux armgcc
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES targets/MKE17Z9/src/startup/arm/startup_MKE17Z9.S
        TOOLCHAINS mdk
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_include(
        INCLUDES ../../devices/MKE17Z9
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.MKE17Z9_sources)
    mcux_component_version(2.7.0)
    mcux_add_source(
        SOURCES targets/MKE17Z9/src/bootloader_config.h
                targets/MKE17Z9/src/bl_clock_config_MKE17Z9.c
                targets/MKE17Z9/src/hardware_init_MKE17Z9.c
                targets/MKE17Z9/src/memory_map_MKE17Z9.c
                targets/MKE17Z9/src/bl_peripherals_MKE17Z9.c
                targets/MKE17Z9/src/peripherals_pinmux.h
                targets/MKE17Z9/src/target_config.h
                targets/common/src/pinmux_utility_common.c
                targets/common/src/bl_lpi2c_irq_config_common.c
                targets/common/src/bl_lpuart_irq_config_common.c
                targets/common/src/bl_lpspi_irq_config_common.c
                src/bootloader/src/lpuart_peripheral_interface_MKE17Z512.c
                src/bootloader/src/lpspi_peripheral_interface_MKE17Z512.c
                src/bootloader/src/lpi2c_peripheral_interface_MKE17Z512.c
                src/memory/src/sram_init_cm0plus.c
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_include(
        INCLUDES targets/MKE17Z9/src
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.MIMXRT1052_startup)
    mcux_component_version(2.7.0)
    mcux_add_source(
        SOURCES ../../devices/RT/RT1050/MIMXRT1052/system_MIMXRT1052.h
                targets/MIMXRT1052/src/startup/system_MIMXRT1052.c
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES targets/MIMXRT1052/src/startup/iar/startup_MIMXRT1052.s
        TOOLCHAINS iar
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES targets/MIMXRT1052/src/startup/gcc/startup_MIMXRT1052.S
        TOOLCHAINS mcux armgcc
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES src/startup/crt0_gcc.S
        TOOLCHAINS mcux armgcc
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES targets/MIMXRT1052/src/startup/arm/startup_MIMXRT1052.s
        TOOLCHAINS mdk
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_include(
        INCLUDES ../../devices/MIMXRT1052
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.MIMXRT1052_sources)
    mcux_component_version(2.7.0)
    mcux_add_source(
        SOURCES targets/MIMXRT1052/src/bootloader_config.h
                targets/MIMXRT1052/src/bl_clock_config_MIMXRT1052.c
                targets/MIMXRT1052/src/hardware_init_MIMXRT1052.c
                targets/MIMXRT1052/src/memory_map_MIMXRT1052.c
                targets/MIMXRT1052/src/external_memory_property_map_MIMXRT1052.c
                targets/MIMXRT1052/src/flexspi_nand_config_MIMXRT1052.c
                targets/MIMXRT1052/src/flexspi_nor_config_MIMXRT1052.c
                targets/MIMXRT1052/src/semc_nand_config_MIMXRT1052.c
                targets/MIMXRT1052/src/semc_nor_config_MIMXRT1052.c
                targets/MIMXRT1052/src/bl_peripherals_MIMXRT1052.c
                targets/MIMXRT1052/src/peripherals_pinmux.h
                targets/MIMXRT1052/src/target_config.h
                targets/MIMXRT1052/src/fusemap.h
                targets/common/src/pinmux_utility_imxrt_series.c
                targets/MIMXRT1052/src/bl_lpuart_irq_config_MIMXRT1052.c
                targets/MIMXRT1052/src/sdmmc_init.h
                targets/MIMXRT1052/src/sdmmc_config_MIMXRT1052.c
                targets/MIMXRT1052/src/usb_device_config.h
                targets/MIMXRT1052/src/sram_init_MIMXRT1052.c
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES ../../devices/MIMXRT1052/drivers/fsl_iomuxc.h
        TOOLCHAINS mcux
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_include(
        INCLUDES targets/MIMXRT1052/src
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_include(
        TOOLCHAINS mcux
        INCLUDES devices/MIMXRT1052/drivers
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.MIMXRT1021_startup)
    mcux_component_version(2.7.0)
    mcux_add_source(
        SOURCES ../../devices/RT/RT1020/MIMXRT1021/system_MIMXRT1021.h
                targets/MIMXRT1021/src/startup/system_MIMXRT1021.c
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES targets/MIMXRT1021/src/startup/iar/startup_MIMXRT1021.s
        TOOLCHAINS iar
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES targets/MIMXRT1021/src/startup/gcc/startup_MIMXRT1021.S
        TOOLCHAINS mcux armgcc
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES src/startup/crt0_gcc.S
        TOOLCHAINS mcux armgcc
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES targets/MIMXRT1021/src/startup/arm/startup_MIMXRT1021.s
        TOOLCHAINS mdk
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_include(
        INCLUDES ../../devices/MIMXRT1021
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.MIMXRT1021_sources)
    mcux_component_version(2.7.0)
    mcux_add_source(
        SOURCES targets/MIMXRT1021/src/bl_api.c
                targets/MIMXRT1021/src/bl_api.h
                targets/MIMXRT1021/src/bootloader_config.h
                targets/MIMXRT1021/src/bl_clock_config_MIMXRT1021.c
                targets/MIMXRT1021/src/hardware_init_MIMXRT1021.c
                targets/MIMXRT1021/src/memory_map_MIMXRT1021.c
                targets/MIMXRT1021/src/external_memory_property_map_MIMXRT1021.c
                targets/MIMXRT1021/src/flexspi_nand_config_MIMXRT1021.c
                targets/MIMXRT1021/src/flexspi_nor_config_MIMXRT1021.c
                targets/MIMXRT1021/src/semc_nand_config_MIMXRT1021.c
                targets/MIMXRT1021/src/semc_nor_config_MIMXRT1021.c
                targets/MIMXRT1021/src/bl_peripherals_MIMXRT1021.c
                targets/MIMXRT1021/src/peripherals_pinmux.h
                targets/MIMXRT1021/src/target_config.h
                targets/MIMXRT1021/src/fusemap.h
                targets/common/src/pinmux_utility_imxrt_series.c
                targets/MIMXRT1021/src/bl_lpuart_irq_config_MIMXRT1021.c
                targets/MIMXRT1021/src/sdmmc_init.h
                targets/MIMXRT1021/src/sdmmc_config_MIMXRT1021.c
                targets/MIMXRT1021/src/usb_device_config.h
                targets/MIMXRT1021/src/sram_init_MIMXRT1021.c
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_include(
        INCLUDES targets/MIMXRT1021/src
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.MIMXRT1062_drivers)
    mcux_component_version(2.7.0)
    mcux_add_source(
        SOURCES targets/MIMXRT1062/src/fsl_wdog.h
                targets/MIMXRT1062/src/fsl_rtwdog.h
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_include(
        INCLUDES targets/MIMXRT1062/src
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.MIMXRT1062_startup)
    mcux_component_version(2.7.0)
    mcux_add_source(
        SOURCES ../../devices/RT/RT1060/MIMXRT1062/system_MIMXRT1062.h
                targets/MIMXRT1062/src/startup/system_MIMXRT1062.c
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES targets/MIMXRT1062/src/startup/iar/startup_MIMXRT1062.s
        TOOLCHAINS iar
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES targets/MIMXRT1062/src/startup/gcc/startup_MIMXRT1062.S
        TOOLCHAINS mcux armgcc
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES src/startup/crt0_gcc.S
        TOOLCHAINS mcux armgcc
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES targets/MIMXRT1062/src/startup/arm/startup_MIMXRT1062.s
        TOOLCHAINS mdk
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_include(
        INCLUDES ../../devices/MIMXRT1062
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.MIMXRT1062_sources)
    mcux_component_version(2.7.0)
    mcux_add_source(
        SOURCES targets/MIMXRT1062/src/bl_api.c
                targets/MIMXRT1062/src/bl_api.h
                targets/MIMXRT1062/src/bootloader_config.h
                targets/MIMXRT1062/src/bl_clock_config_MIMXRT1062.c
                targets/MIMXRT1062/src/hardware_init_MIMXRT1062.c
                targets/MIMXRT1062/src/memory_map_MIMXRT1062.c
                targets/MIMXRT1062/src/external_memory_property_map_MIMXRT1062.c
                targets/MIMXRT1062/src/flexspi_nand_config_MIMXRT1062.c
                targets/MIMXRT1062/src/flexspi_nor_config_MIMXRT1062.c
                targets/MIMXRT1062/src/semc_nand_config_MIMXRT1062.c
                targets/MIMXRT1062/src/semc_nor_config_MIMXRT1062.c
                targets/MIMXRT1062/src/bl_peripherals_MIMXRT1062.c
                targets/MIMXRT1062/src/peripherals_pinmux.h
                targets/MIMXRT1062/src/target_config.h
                targets/MIMXRT1062/src/fusemap.h
                targets/common/src/pinmux_utility_imxrt_series.c
                targets/MIMXRT1062/src/bl_lpuart_irq_config_MIMXRT1062.c
                targets/MIMXRT1062/src/sdmmc_init.h
                targets/MIMXRT1062/src/sdmmc_config_MIMXRT1062.c
                targets/MIMXRT1062/src/usb_device_config.h
                targets/MIMXRT1062/src/sram_init_MIMXRT1062.c
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_include(
        INCLUDES targets/MIMXRT1062/src
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.MIMXRT1064_drivers)
    mcux_component_version(2.7.0)
    mcux_add_source(
        SOURCES targets/MIMXRT1064/src/fsl_wdog.h
                targets/MIMXRT1064/src/fsl_rtwdog.h
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_include(
        INCLUDES targets/MIMXRT1064/src
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.MIMXRT1064_startup)
    mcux_component_version(2.7.0)
    mcux_add_source(
        SOURCES ../../devices/RT/RT1064/MIMXRT1064/system_MIMXRT1064.h
                targets/MIMXRT1064/src/startup/system_MIMXRT1064.c
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES targets/MIMXRT1064/src/startup/iar/startup_MIMXRT1064.s
        TOOLCHAINS iar
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES targets/MIMXRT1064/src/startup/gcc/startup_MIMXRT1064.S
        TOOLCHAINS mcux armgcc
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES src/startup/crt0_gcc.S
        TOOLCHAINS mcux armgcc
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES targets/MIMXRT1064/src/startup/arm/startup_MIMXRT1064.s
        TOOLCHAINS mdk
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_include(
        INCLUDES ../../devices/MIMXRT1064
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.MIMXRT1064_sources)
    mcux_component_version(2.7.0)
    mcux_add_source(
        SOURCES targets/MIMXRT1064/src/bl_api.c
                targets/MIMXRT1064/src/bl_api.h
                targets/MIMXRT1064/src/bootloader_config.h
                targets/MIMXRT1064/src/bl_clock_config_MIMXRT1064.c
                targets/MIMXRT1064/src/hardware_init_MIMXRT1064.c
                targets/MIMXRT1064/src/memory_map_MIMXRT1064.c
                targets/MIMXRT1064/src/external_memory_property_map_MIMXRT1064.c
                targets/MIMXRT1064/src/flexspi_nand_config_MIMXRT1064.c
                targets/MIMXRT1064/src/flexspi_nor_config_MIMXRT1064.c
                targets/MIMXRT1064/src/semc_nand_config_MIMXRT1064.c
                targets/MIMXRT1064/src/semc_nor_config_MIMXRT1064.c
                targets/MIMXRT1064/src/bl_peripherals_MIMXRT1064.c
                targets/MIMXRT1064/src/peripherals_pinmux.h
                targets/MIMXRT1064/src/target_config.h
                targets/MIMXRT1064/src/fusemap.h
                targets/common/src/pinmux_utility_imxrt_series.c
                targets/MIMXRT1064/src/bl_lpuart_irq_config_MIMXRT1064.c
                targets/MIMXRT1064/src/sdmmc_init.h
                targets/MIMXRT1064/src/sdmmc_config_MIMXRT1064.c
                targets/MIMXRT1064/src/usb_device_config.h
                targets/MIMXRT1064/src/sram_init_MIMXRT1064.c
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_include(
        INCLUDES targets/MIMXRT1064/src
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.MIMXRT1042_drivers)
    mcux_component_version(2.7.0)
    mcux_add_source(
        SOURCES targets/MIMXRT1042/src/fsl_wdog.h
                targets/MIMXRT1042/src/fsl_rtwdog.h
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_include(
        INCLUDES targets/MIMXRT1042/src
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.MIMXRT1042_startup)
    mcux_component_version(2.7.0)
    mcux_add_source(
        SOURCES ../../devices/RT/RT1040/MIMXRT1042/system_MIMXRT1042.h
                targets/MIMXRT1042/src/startup/system_MIMXRT1042.c
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES targets/MIMXRT1042/src/startup/iar/startup_MIMXRT1042.s
        TOOLCHAINS iar
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES targets/MIMXRT1042/src/startup/gcc/startup_MIMXRT1042.S
        TOOLCHAINS mcux armgcc
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES src/startup/crt0_gcc.S
        TOOLCHAINS mcux armgcc
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES targets/MIMXRT1042/src/startup/arm/startup_MIMXRT1042.s
        TOOLCHAINS mdk
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_include(
        INCLUDES ../../devices/MIMXRT1042
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.MIMXRT1042_sources)
    mcux_component_version(2.7.0)
    mcux_add_source(
        SOURCES targets/MIMXRT1042/src/bl_api.c
                targets/MIMXRT1042/src/bl_api.h
                targets/MIMXRT1042/src/bootloader_config.h
                targets/MIMXRT1042/src/bl_clock_config_MIMXRT1042.c
                targets/MIMXRT1042/src/hardware_init_MIMXRT1042.c
                targets/MIMXRT1042/src/memory_map_MIMXRT1042.c
                targets/MIMXRT1042/src/external_memory_property_map_MIMXRT1042.c
                targets/MIMXRT1042/src/flexspi_nand_config_MIMXRT1042.c
                targets/MIMXRT1042/src/flexspi_nor_config_MIMXRT1042.c
                targets/MIMXRT1042/src/semc_nand_config_MIMXRT1042.c
                targets/MIMXRT1042/src/semc_nor_config_MIMXRT1042.c
                targets/MIMXRT1042/src/bl_peripherals_MIMXRT1042.c
                targets/MIMXRT1042/src/peripherals_pinmux.h
                targets/MIMXRT1042/src/target_config.h
                targets/MIMXRT1042/src/fusemap.h
                targets/common/src/pinmux_utility_imxrt_series.c
                targets/MIMXRT1042/src/bl_lpuart_irq_config_MIMXRT1042.c
                targets/MIMXRT1042/src/sdmmc_init.h
                targets/MIMXRT1042/src/sdmmc_config_MIMXRT1042.c
                targets/MIMXRT1042/src/usb_device_config.h
                targets/MIMXRT1042/src/sram_init_MIMXRT1042.c
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_include(
        INCLUDES targets/MIMXRT1042/src
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.MIMXRT1015_startup)
    mcux_component_version(2.7.0)
    mcux_add_source(
        SOURCES ../../devices/RT/RT1015/MIMXRT1015/system_MIMXRT1015.h
                targets/MIMXRT1015/src/startup/system_MIMXRT1015.c
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES targets/MIMXRT1015/src/startup/iar/startup_MIMXRT1015.s
        TOOLCHAINS iar
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES targets/MIMXRT1015/src/startup/gcc/startup_MIMXRT1015.S
        TOOLCHAINS mcux armgcc
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES src/startup/crt0_gcc.S
        TOOLCHAINS mcux armgcc
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES targets/MIMXRT1015/src/startup/arm/startup_MIMXRT1015.s
        TOOLCHAINS mdk
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_include(
        INCLUDES ../../devices/MIMXRT1015
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.MIMXRT1015_sources)
    mcux_component_version(2.7.0)
    mcux_add_source(
        SOURCES targets/MIMXRT1015/src/bootloader_config.h
                targets/MIMXRT1015/src/bl_clock_config_MIMXRT1015.c
                targets/MIMXRT1015/src/hardware_init_MIMXRT1015.c
                targets/MIMXRT1015/src/memory_map_MIMXRT1015.c
                targets/MIMXRT1015/src/external_memory_property_map_MIMXRT1015.c
                targets/MIMXRT1015/src/flexspi_nand_config_MIMXRT1015.c
                targets/MIMXRT1015/src/flexspi_nor_config_MIMXRT1015.c
                targets/MIMXRT1015/src/bl_peripherals_MIMXRT1015.c
                targets/MIMXRT1015/src/peripherals_pinmux.h
                targets/MIMXRT1015/src/target_config.h
                targets/MIMXRT1015/src/fusemap.h
                targets/common/src/pinmux_utility_imxrt_series.c
                targets/MIMXRT1015/src/bl_lpuart_irq_config_MIMXRT1015.c
                targets/MIMXRT1015/src/usb_device_config.h
                targets/MIMXRT1015/src/sram_init_MIMXRT1015.c
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_include(
        INCLUDES targets/MIMXRT1015/src
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.MIMXRT1011_drivers)
    mcux_component_version(2.7.0)
    mcux_add_source(
        SOURCES ../../devices/RT/RT1010/MIMXRT1011/drivers/fsl_clock.h
                ../../drivers/wdog01/fsl_wdog.h
                ../../drivers/rtwdog/fsl_rtwdog.h
                ../../devices/RT/RT1010/MIMXRT1011/drivers/fsl_iomuxc.h
                # ../../drivers/igpio/fsl_gpio.h
                # ../../drivers/igpio/fsl_gpio.c
                ../../drivers/lpuart/fsl_lpuart.h
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_include(
        INCLUDES ../../drivers/common
                 ../../devices/RT/RT1010/MIMXRT1011/drivers
                 ../../drivers/wdog01
                 ../../drivers/rtwdog
                 ../../drivers/igpio
                 ../../drivers/lpuart
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.MIMXRT1011_startup)
    mcux_component_version(2.7.0)
    mcux_add_source(
        SOURCES ../../devices/RT/RT1010/MIMXRT1011/fsl_device_registers.h
                ../../devices/RT/RT1010/MIMXRT1011/system_MIMXRT1011.h
                targets/MIMXRT1011/src/startup/system_MIMXRT1011.c
                ../../devices/RT/RT1010/MIMXRT1011/MIMXRT1011.h
                ../../devices/RT/RT1010/MIMXRT1011/MIMXRT1011_features.h
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES targets/MIMXRT1011/src/startup/iar/startup_MIMXRT1011.s
        TOOLCHAINS iar
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES targets/MIMXRT1011/src/startup/gcc/startup_MIMXRT1011.S
        TOOLCHAINS mcux armgcc
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES src/startup/crt0_gcc.S
        TOOLCHAINS mcux armgcc
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES targets/MIMXRT1011/src/startup/arm/startup_MIMXRT1011.s
        TOOLCHAINS mdk
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_include(
        INCLUDES ../../devices/RT/RT1010/MIMXRT1011/
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.MIMXRT1011_sources)
    mcux_component_version(2.7.0)
    mcux_add_source(
        SOURCES targets/MIMXRT1011/src/bootloader_config.h
                targets/MIMXRT1011/src/bl_clock_config_MIMXRT1011.c
                targets/MIMXRT1011/src/hardware_init_MIMXRT1011.c
                targets/MIMXRT1011/src/memory_map_MIMXRT1011.c
                targets/MIMXRT1011/src/external_memory_property_map_MIMXRT1011.c
                targets/MIMXRT1011/src/flexspi_nor_flash_MIMXRT1011.c
                targets/MIMXRT1011/src/bl_peripherals_MIMXRT1011.c
                targets/MIMXRT1011/src/peripherals_pinmux.h
                targets/MIMXRT1011/src/target_config.h
                targets/MIMXRT1011/src/fusemap.h
                targets/common/src/pinmux_utility_imxrt_series.c
                targets/MIMXRT1011/src/bl_lpuart_irq_config_MIMXRT1011.c
                targets/MIMXRT1011/src/usb_device_config.h
                targets/MIMXRT1011/src/sram_init_MIMXRT1011.c
                targets/MIMXRT1011/src/bl_dcp_MIMXRT1011.c
                targets/MIMXRT1011/src/bl_romapi_MIMXRT1011.c
                src/bootloader/src/lpuart_peripheral_interface.c
                src/bootloader/src/bl_nor_encrypt_otfad.c
                src/bootloader/src/usb_hid_msc_peripheral_interface.c
                src/bootloader/bl_nor_encrypt.h
                src/memory/src/flexspi_nor_memory.c
                src/memory/src/flexspi_nor_memory.h
                src/property/src/property_imx.c
                src/drivers/flexspi_nor/flexspi_nor_flash.h
                src/drivers/flexspi/bl_flexspi.h
                src/drivers/smc/smc.h
                src/drivers/dcp/bl_dcp.h
                src/drivers/trng/bl_trng.h
                src/bootloader/bl_keyblob.h
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_include(
        INCLUDES targets/MIMXRT1011/src
                 src/bootloader
                 src/memory/src
                 src/drivers/flexspi_nor
                 src/drivers/flexspi
                 src/drivers/smc
                 src/drivers/dcp
                 src/drivers/trng
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.MIMXRT1024_startup)
    mcux_component_version(2.7.0)
    mcux_add_source(
        SOURCES ../../devices/RT/RT1020/MIMXRT1024/system_MIMXRT1024.h
                targets/MIMXRT1024/src/startup/system_MIMXRT1024.c
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES targets/MIMXRT1024/src/startup/iar/startup_MIMXRT1024.s
        TOOLCHAINS iar
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES targets/MIMXRT1024/src/startup/gcc/startup_MIMXRT1024.S
        TOOLCHAINS mcux armgcc
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES src/startup/crt0_gcc.S
        TOOLCHAINS mcux armgcc
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES targets/MIMXRT1024/src/startup/arm/startup_MIMXRT1024.S
        TOOLCHAINS mdk
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_include(
        INCLUDES ../../devices/MIMXRT1024
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.MIMXRT1024_sources)
    mcux_component_version(2.7.0)
    mcux_add_source(
        SOURCES targets/MIMXRT1024/src/bl_api.c
                targets/MIMXRT1024/src/bl_api.h
                targets/MIMXRT1024/src/bootloader_config.h
                targets/MIMXRT1024/src/bl_clock_config_MIMXRT1024.c
                targets/MIMXRT1024/src/hardware_init_MIMXRT1024.c
                targets/MIMXRT1024/src/memory_map_MIMXRT1024.c
                targets/MIMXRT1024/src/external_memory_property_map_MIMXRT1024.c
                targets/MIMXRT1024/src/flexspi_nor_config_MIMXRT1024.c
                targets/MIMXRT1024/src/bl_peripherals_MIMXRT1024.c
                targets/MIMXRT1024/src/peripherals_pinmux.h
                targets/MIMXRT1024/src/target_config.h
                targets/MIMXRT1024/src/fusemap.h
                targets/common/src/pinmux_utility_imxrt_series.c
                targets/MIMXRT1024/src/bl_lpuart_irq_config_MIMXRT1024.c
                targets/MIMXRT1024/src/usb_device_config.h
                targets/MIMXRT1024/src/sram_init_MIMXRT1024.c
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_include(
        INCLUDES targets/MIMXRT1024/src
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.MIMXRT1176_startup)
    mcux_component_version(2.7.0)
    mcux_add_source(
        SOURCES ../../devices/RT/RT1170/MIMXRT1176/system_MIMXRT1176_cm4.h
        CORES cm4f
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES ../../devices/RT/RT1170/MIMXRT1176/system_MIMXRT1176_cm7.h
        CORES cm7f
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES targets/MIMXRT1176/src/startup/system_MIMXRT1176_cm4.c
        CORES cm4f
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES targets/MIMXRT1176/src/startup/system_MIMXRT1176_cm7.c
        CORES cm7f
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES targets/MIMXRT1176/src/startup/iar/startup_MIMXRT1176_cm4.s
        TOOLCHAINS iar
        CORES cm4f
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES targets/MIMXRT1176/src/startup/iar/startup_MIMXRT1176_cm7.s
        TOOLCHAINS iar
        CORES cm7f
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES targets/MIMXRT1176/src/startup/gcc/startup_MIMXRT1176_cm4.S
        TOOLCHAINS mcux armgcc
        CORES cm4f
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES targets/MIMXRT1176/src/startup/gcc/startup_MIMXRT1176_cm7.S
        TOOLCHAINS mcux armgcc
        CORES cm7f
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES src/startup/crt0_gcc.S
        TOOLCHAINS mcux armgcc
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES targets/MIMXRT1176/src/startup/arm/startup_MIMXRT1176_cm4.S
        TOOLCHAINS mdk
        CORES cm4f
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES targets/MIMXRT1176/src/startup/arm/startup_MIMXRT1176_cm7.S
        TOOLCHAINS mdk
        CORES cm7f
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_include(
        INCLUDES ../../devices/MIMXRT1176
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.MIMXRT1176_sources)
    mcux_component_version(2.7.0)
    mcux_add_source(
        SOURCES targets/MIMXRT1176/src/bl_lpuart_irq_config_MIMXRT1176.c
                targets/MIMXRT1176/src/bl_mpu.h
                targets/MIMXRT1176/src/bootloader_config.h
                targets/MIMXRT1176/src/clock_cfg_MIMXRT1176.c
                targets/MIMXRT1176/src/external_memory_property_map_MIMXRT1176.c
                targets/MIMXRT1176/src/flexspi_config_MIMXRT1176.c
                targets/MIMXRT1176/src/flexspi_nand_config_MIMXRT1176.c
                targets/MIMXRT1176/src/flexspi_nor_config_MIMXRT1176.c
                targets/MIMXRT1176/src/fusemap.h
                targets/MIMXRT1176/src/hardware_init_MIMXRT1176.c
                targets/MIMXRT1176/src/memory_config.h
                targets/MIMXRT1176/src/memory_map_MIMXRT1176.c
                targets/MIMXRT1176/src/ocotp_MIMXRT1176.c
                targets/MIMXRT1176/src/periph_MIMXRT1176.c
                targets/MIMXRT1176/src/peripherals_pinmux.h
                targets/MIMXRT1176/src/sdmmc_config_MIMXRT1176.c
                targets/MIMXRT1176/src/sdmmc_convert_MIMXRT1176.c
                targets/MIMXRT1176/src/sdmmc_init.h
                targets/MIMXRT1176/src/security_config_MIMXRT1176.c
                targets/MIMXRT1176/src/semc_nand_config_MIMXRT1176.c
                targets/MIMXRT1176/src/target_config.h
                targets/common/src/pinmux_utility_imxrt_series.c
                targets/MIMXRT1176/src/usb_device_config.h
                targets/MIMXRT1176/src/sram_init_MIMXRT1176.c
                src/bootloader/src/lpuart_peripheral_interface.c
                src/bootloader/src/usb_hid_msc_peripheral_interface.c
                src/property/src/property_imx.c
                src/security/keyblob/src/keyblob_caam.c
                src/security/keyblob/src/keyblob.c
                src/security/keyblob/keyblob.h
                src/bootloader/bl_keyblob.h
                src/authentication/key_store_puf.c
                src/authentication/key_store_puf.h
                src/memory/src/semc_nand_memory.c
                src/memory/src/semc_nand_memory.h
                src/drivers/nand_ecc/nand_ecc.c
                src/drivers/nand_ecc/nand_ecc.h
                src/drivers/semc/bl_semc.c
                src/drivers/semc/bl_semc.h
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_include(
        INCLUDES targets/MIMXRT1176/src
                 src
                 src/bootloader
                 src/include
                 src/startup
                 src/memory
                 src/memory/src
                 src/property
                 src/authentication
                 src/security/keyblob
                 src/drivers
                 src/drivers/flexspi_nor
                 src/drivers/flexspi
                 src/drivers/serial_nor_eeprom
                 src/drivers/sdmmc/inc
                 src/drivers/semc
                 src/drivers/nand_ecc
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.MIMXRT1166_startup)
    mcux_component_version(2.7.0)
    mcux_add_source(
        SOURCES ../../devices/RT/RT1160/MIMXRT1166/system_MIMXRT1166_cm4.h
        CORES cm4f
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES ../../devices/RT/RT1160/MIMXRT1166/system_MIMXRT1166_cm7.h
        CORES cm7f
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES targets/MIMXRT1166/src/startup/system_MIMXRT1166_cm4.c
        CORES cm4f
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES targets/MIMXRT1166/src/startup/system_MIMXRT1166_cm7.c
        CORES cm7f
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES targets/MIMXRT1166/src/startup/iar/startup_MIMXRT1166_cm4.s
        TOOLCHAINS iar
        CORES cm4f
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES targets/MIMXRT1166/src/startup/iar/startup_MIMXRT1166_cm7.s
        TOOLCHAINS iar
        CORES cm7f
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES targets/MIMXRT1166/src/startup/gcc/startup_MIMXRT1166_cm4.S
        TOOLCHAINS mcux armgcc
        CORES cm4f
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES targets/MIMXRT1166/src/startup/gcc/startup_MIMXRT1166_cm7.S
        TOOLCHAINS mcux armgcc
        CORES cm7f
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES src/startup/crt0_gcc.S
        TOOLCHAINS mcux armgcc
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES targets/MIMXRT1166/src/startup/arm/startup_MIMXRT1166_cm4.S
        TOOLCHAINS mdk
        CORES cm4f
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES targets/MIMXRT1166/src/startup/arm/startup_MIMXRT1166_cm7.S
        TOOLCHAINS mdk
        CORES cm7f
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_include(
        INCLUDES ../../devices/MIMXRT1166
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.MIMXRT1166_sources)
    mcux_component_version(2.7.0)
    mcux_add_source(
        SOURCES targets/MIMXRT1166/src/bl_lpuart_irq_config_MIMXRT1166.c
                targets/MIMXRT1166/src/bl_mpu.h
                targets/MIMXRT1166/src/bootloader_config.h
                targets/MIMXRT1166/src/clock_cfg_MIMXRT1166.c
                targets/MIMXRT1166/src/external_memory_property_map_MIMXRT1166.c
                targets/MIMXRT1166/src/flexspi_config_MIMXRT1166.c
                targets/MIMXRT1166/src/flexspi_nand_config_MIMXRT1166.c
                targets/MIMXRT1166/src/flexspi_nor_config_MIMXRT1166.c
                targets/MIMXRT1166/src/fusemap.h
                targets/MIMXRT1166/src/hardware_init_MIMXRT1166.c
                targets/MIMXRT1166/src/memory_config.h
                targets/MIMXRT1166/src/memory_map_MIMXRT1166.c
                targets/MIMXRT1166/src/ocotp_MIMXRT1166.c
                targets/MIMXRT1166/src/periph_MIMXRT1166.c
                targets/MIMXRT1166/src/peripherals_pinmux.h
                targets/MIMXRT1166/src/sdmmc_config_MIMXRT1166.c
                targets/MIMXRT1166/src/sdmmc_convert_MIMXRT1166.c
                targets/MIMXRT1166/src/sdmmc_init.h
                targets/MIMXRT1166/src/security_config_MIMXRT1166.c
                targets/MIMXRT1166/src/semc_nand_config_MIMXRT1166.c
                targets/MIMXRT1166/src/target_config.h
                targets/common/src/pinmux_utility_imxrt_series.c
                targets/MIMXRT1166/src/usb_device_config.h
                targets/MIMXRT1166/src/sram_init_MIMXRT1166.c
                src/bootloader/src/lpuart_peripheral_interface.c
                src/bootloader/src/usb_hid_msc_peripheral_interface.c
                src/property/src/property_imx.c
                src/security/keyblob/src/keyblob_caam.c
                src/security/keyblob/src/keyblob.c
                src/security/keyblob/keyblob.h
                src/bootloader/bl_keyblob.h
                src/authentication/key_store_puf.c
                src/authentication/key_store_puf.h
                src/memory/src/semc_nand_memory.c
                src/memory/src/semc_nand_memory.h
                src/drivers/nand_ecc/nand_ecc.c
                src/drivers/nand_ecc/nand_ecc.h
                src/drivers/semc/bl_semc.c
                src/drivers/semc/bl_semc.h
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_include(
        INCLUDES targets/MIMXRT1166/src
                 src
                 src/bootloader
                 src/include
                 src/startup
                 src/memory
                 src/memory/src
                 src/property
                 src/authentication
                 src/security/keyblob
                 src/drivers
                 src/drivers/flexspi_nor
                 src/drivers/flexspi
                 src/drivers/serial_nor_eeprom
                 src/drivers/sdmmc/inc
                 src/drivers/semc
                 src/drivers/nand_ecc
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.MIMXRT1189_startup)
    mcux_component_version(2.7.0)
    mcux_add_source(
        SOURCES ../../devices/RT/RT1180/MIMXRT1189/system_MIMXRT1189_cm33.h
        CORES cm33
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES targets/MIMXRT1189/src/startup/system_MIMXRT1189_cm33.c
        CORES cm33
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES targets/MIMXRT1189/src/startup/iar/startup_MIMXRT1189_cm33.s
        TOOLCHAINS iar
        CORES cm33
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES targets/MIMXRT1189/src/startup/gcc/startup_MIMXRT1189_cm33.S
        TOOLCHAINS mcux armgcc
        CORES cm33
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES src/startup/crt0_gcc.S
        TOOLCHAINS mcux armgcc
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES ../../devices/RT/RT1180/MIMXRT1189/arm/startup_MIMXRT1189_cm33.S
        TOOLCHAINS mdk
        CORES cm33
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_include(
        INCLUDES ../../devices/MIMXRT1189
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.MIMXRT1189_sources)
    mcux_component_version(2.7.0)
    mcux_add_source(
        SOURCES targets/MIMXRT1189/src/bl_lpuart_irq_config_MIMXRT1189.c
                targets/MIMXRT1189/src/bl_lpspi_irq_config_MIMXRT1189.c
                targets/MIMXRT1189/src/bootloader_config.h
                targets/MIMXRT1189/src/clock_cfg_MIMXRT1189.c
                targets/MIMXRT1189/src/external_memory_property_map_MIMXRT1189.c
                targets/MIMXRT1189/src/flexspi_config_MIMXRT1189.c
                targets/MIMXRT1189/src/flexspi_nand_config_MIMXRT1189.c
                targets/MIMXRT1189/src/flexspi_nor_config_MIMXRT1189.c
                targets/MIMXRT1189/src/fusemap.h
                targets/MIMXRT1189/src/hardware_init_MIMXRT1189.c
                targets/MIMXRT1189/src/lpspi_mem_config_MIMXRT1189.c
                targets/MIMXRT1189/src/memory_config.h
                targets/MIMXRT1189/src/memory_map_MIMXRT1189.c
                targets/MIMXRT1189/src/periph_MIMXRT1189.c
                targets/MIMXRT1189/src/peripherals_pinmux.h
                targets/MIMXRT1189/src/sdmmc_config_MIMXRT1189.c
                targets/MIMXRT1189/src/sdmmc_convert_MIMXRT1189.c
                targets/MIMXRT1189/src/sdmmc_init.h
                targets/MIMXRT1189/src/semc_nand_config_MIMXRT1189.c
                targets/MIMXRT1189/src/edgelock_config_MIMXRT1189.c
                targets/MIMXRT1189/src/target_config.h
                targets/common/src/pinmux_utility_imxrt_series.c
                targets/MIMXRT1189/src/usb_device_config.h
                targets/MIMXRT1189/src/sram_init_MIMXRT1189.c
                src/bootloader/src/lpuart_peripheral_interface.c
                src/bootloader/src/lpspi_peripheral_interface.c
                src/bootloader/src/usb_hid_msc_peripheral_interface.c
                src/property/src/property_imx.c
                src/memory/src/semc_nand_memory.c
                src/memory/src/semc_nand_memory.h
                src/drivers/nand_ecc/nand_ecc.c
                src/drivers/nand_ecc/nand_ecc.h
                src/drivers/semc/bl_semc.c
                src/drivers/semc/bl_semc.h
                src/security/keyblob/src/keyblob_edgelock.c
                src/security/keyblob/src/keyblob.c
                src/security/keyblob/keyblob.h
                src/bootloader/bl_keyblob.h
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_include(
        INCLUDES targets/MIMXRT1189/src
                 src/security/keyblob
                 src
                 src/bootloader
                 src/include
                 src/startup
                 src/memory
                 src/memory/src
                 src/property
                 src/drivers
                 src/drivers/flexspi_nor
                 src/drivers/flexspi
                 src/drivers/serial_nor_eeprom
                 src/drivers/sdmmc/inc
                 src/drivers/semc
                 src/drivers/nand_ecc
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.MIMXRT1187_startup)
    mcux_component_version(2.7.0)
    mcux_add_source(
        SOURCES ../../devices/MIMXRT1187/system_MIMXRT1187_cm33.h
        CORES cm33
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES targets/MIMXRT1187/src/startup/system_MIMXRT1187_cm33.c
        CORES cm33
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES targets/MIMXRT1187/src/startup/iar/startup_MIMXRT1187_cm33.s
        TOOLCHAINS iar
        CORES cm33
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES targets/MIMXRT1187/src/startup/gcc/startup_MIMXRT1187_cm33.S
        TOOLCHAINS mcux armgcc
        CORES cm33
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES src/startup/crt0_gcc.S
        TOOLCHAINS mcux armgcc
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES ../../devices/MIMXRT1187/arm/startup_MIMXRT1187_cm33.S
        TOOLCHAINS mdk
        CORES cm33
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_include(
        INCLUDES ../../devices/MIMXRT1187
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.MIMXRT1187_sources)
    mcux_component_version(2.7.0)
    mcux_add_source(
        SOURCES targets/MIMXRT1187/src/bl_lpuart_irq_config_MIMXRT1187.c
                targets/MIMXRT1187/src/bl_lpspi_irq_config_MIMXRT1187.c
                targets/MIMXRT1187/src/bootloader_config.h
                targets/MIMXRT1187/src/clock_cfg_MIMXRT1187.c
                targets/MIMXRT1187/src/external_memory_property_map_MIMXRT1187.c
                targets/MIMXRT1187/src/flexspi_config_MIMXRT1187.c
                targets/MIMXRT1187/src/flexspi_nand_config_MIMXRT1187.c
                targets/MIMXRT1187/src/flexspi_nor_config_MIMXRT1187.c
                targets/MIMXRT1187/src/fusemap.h
                targets/MIMXRT1187/src/hardware_init_MIMXRT1187.c
                targets/MIMXRT1187/src/lpspi_mem_config_MIMXRT1187.c
                targets/MIMXRT1187/src/memory_config.h
                targets/MIMXRT1187/src/memory_map_MIMXRT1187.c
                targets/MIMXRT1187/src/periph_MIMXRT1187.c
                targets/MIMXRT1187/src/peripherals_pinmux.h
                targets/MIMXRT1187/src/sdmmc_config_MIMXRT1187.c
                targets/MIMXRT1187/src/sdmmc_convert_MIMXRT1187.c
                targets/MIMXRT1187/src/sdmmc_init.h
                targets/MIMXRT1187/src/semc_nand_config_MIMXRT1187.c
                targets/MIMXRT1187/src/edgelock_config_MIMXRT1187.c
                targets/MIMXRT1187/src/target_config.h
                targets/common/src/pinmux_utility_imxrt_series.c
                targets/MIMXRT1187/src/usb_device_config.h
                targets/MIMXRT1187/src/sram_init_MIMXRT1187.c
                src/bootloader/src/lpuart_peripheral_interface.c
                src/bootloader/src/lpspi_peripheral_interface.c
                src/bootloader/src/usb_hid_msc_peripheral_interface.c
                src/property/src/property_imx.c
                src/memory/src/semc_nand_memory.c
                src/memory/src/semc_nand_memory.h
                src/drivers/nand_ecc/nand_ecc.c
                src/drivers/nand_ecc/nand_ecc.h
                src/drivers/semc/bl_semc.c
                src/drivers/semc/bl_semc.h
                src/security/keyblob/src/keyblob_edgelock.c
                src/security/keyblob/src/keyblob.c
                src/security/keyblob/keyblob.h
                src/bootloader/bl_keyblob.h
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_include(
        INCLUDES targets/MIMXRT1187/src
                 src
                 src/bootloader
                 src/include
                 src/startup
                 src/memory
                 src/memory/src
                 src/property
                 src/drivers
                 src/drivers/flexspi_nor
                 src/drivers/flexspi
                 src/drivers/serial_nor_eeprom
                 src/drivers/sdmmc/inc
                 src/drivers/semc
                 src/drivers/nand_ecc
                 src/security/keyblob
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.MIMXRT1186_startup)
    mcux_component_version(2.7.0)
    mcux_add_source(
        SOURCES ../../devices/RT/RT1180/MIMXRT1186/system_MIMXRT1186_cm33.h
        CORES cm33
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES targets/MIMXRT1186/src/startup/system_MIMXRT1186_cm33.c
        CORES cm33
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES targets/MIMXRT1186/src/startup/iar/startup_MIMXRT1186_cm33.s
        TOOLCHAINS iar
        CORES cm33
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES targets/MIMXRT1186/src/startup/gcc/startup_MIMXRT1186_cm33.S
        TOOLCHAINS mcux armgcc
        CORES cm33
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES src/startup/crt0_gcc.S
        TOOLCHAINS mcux armgcc
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES ../../devices/RT/RT1180/MIMXRT1186/arm/startup_MIMXRT1186_cm33.S
        TOOLCHAINS mdk
        CORES cm33
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_include(
        INCLUDES ../../devices/MIMXRT1186
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.MIMXRT1186_sources)
    mcux_component_version(2.7.0)
    mcux_add_source(
        SOURCES targets/MIMXRT1186/src/bl_lpuart_irq_config_MIMXRT1186.c
                targets/MIMXRT1186/src/bl_lpspi_irq_config_MIMXRT1186.c
                targets/MIMXRT1186/src/bootloader_config.h
                targets/MIMXRT1186/src/clock_cfg_MIMXRT1186.c
                targets/MIMXRT1186/src/external_memory_property_map_MIMXRT1186.c
                targets/MIMXRT1186/src/flexspi_config_MIMXRT1186.c
                targets/MIMXRT1186/src/flexspi_nand_config_MIMXRT1186.c
                targets/MIMXRT1186/src/flexspi_nor_config_MIMXRT1186.c
                targets/MIMXRT1186/src/fusemap.h
                targets/MIMXRT1186/src/hardware_init_MIMXRT1186.c
                targets/MIMXRT1186/src/lpspi_mem_config_MIMXRT1186.c
                targets/MIMXRT1186/src/memory_config.h
                targets/MIMXRT1186/src/memory_map_MIMXRT1186.c
                targets/MIMXRT1186/src/periph_MIMXRT1186.c
                targets/MIMXRT1186/src/peripherals_pinmux.h
                targets/MIMXRT1186/src/sdmmc_config_MIMXRT1186.c
                targets/MIMXRT1186/src/sdmmc_convert_MIMXRT1186.c
                targets/MIMXRT1186/src/sdmmc_init.h
                targets/MIMXRT1186/src/semc_nand_config_MIMXRT1186.c
                targets/MIMXRT1186/src/edgelock_config_MIMXRT1186.c
                targets/MIMXRT1186/src/target_config.h
                targets/common/src/pinmux_utility_imxrt_series.c
                targets/MIMXRT1186/src/usb_device_config.h
                targets/MIMXRT1186/src/sram_init_MIMXRT1186.c
                src/bootloader/src/lpuart_peripheral_interface.c
                src/bootloader/src/lpspi_peripheral_interface.c
                src/bootloader/src/usb_hid_msc_peripheral_interface.c
                src/property/src/property_imx.c
                src/memory/src/semc_nand_memory.c
                src/memory/src/semc_nand_memory.h
                src/drivers/nand_ecc/nand_ecc.c
                src/drivers/nand_ecc/nand_ecc.h
                src/drivers/semc/bl_semc.c
                src/drivers/semc/bl_semc.h
                src/security/keyblob/src/keyblob_edgelock.c
                src/security/keyblob/src/keyblob.c
                src/security/keyblob/keyblob.h
                src/bootloader/bl_keyblob.h
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_include(
        INCLUDES targets/MIMXRT1186/src
                 src/security/keyblob
                 src
                 src/bootloader
                 src/include
                 src/startup
                 src/memory
                 src/memory/src
                 src/property
                 src/drivers
                 src/drivers/flexspi_nor
                 src/drivers/flexspi
                 src/drivers/serial_nor_eeprom
                 src/drivers/sdmmc/inc
                 src/drivers/semc
                 src/drivers/nand_ecc
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.LPC54018_startup)
    mcux_component_version(2.7.0)
    mcux_add_source(
        SOURCES ../../devices/LPC54018/system_LPC54018.h
                targets/LPC54018/src/startup/system_LPC54018.c
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES targets/LPC54018/src/startup/iar/startup_LPC54018.s
        TOOLCHAINS iar
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES targets/LPC54018/src/startup/gcc/startup_LPC54018.S
        TOOLCHAINS mcux armgcc
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES src/startup/crt0.s
        TOOLCHAINS iar
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES src/startup/crt0_gcc.S
        TOOLCHAINS mcux armgcc
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES targets/LPC54018/src/startup/arm/startup_LPC54018.S
        TOOLCHAINS mdk
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_include(
        INCLUDES ../../devices/LPC54018
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.LPC54018_sources)
    mcux_component_version(2.7.0)
    mcux_add_source(
        SOURCES targets/LPC54018/src/bootloader_config.h
                targets/LPC54018/src/bl_clock_config_LPC54018.c
                targets/LPC54018/src/hardware_init_LPC54018.c
                targets/LPC54018/src/memory_map_LPC54018.c
                targets/LPC54018/src/external_memory_property_map_LPC54018.c
                targets/LPC54018/src/bl_peripherals_LPC54018.c
                targets/LPC54018/src/peripherals_pinmux.h
                targets/LPC54018/src/target_config.h
                targets/LPC54018/src/usb_device_config.h
                targets/common/src/pinmux_utility_lpc.c
                targets/common/src/bl_flexcomm_usart_irq_config_common.c
                targets/common/src/bl_flexcomm_i2c_irq_config_common.c
                targets/common/src/bl_flexcomm_spi_irq_config_common.c
                src/bootloader/src/flexcomm_usart_peripheral_interface.c
                src/bootloader/src/flexcomm_i2c_peripheral_interface.c
                src/bootloader/src/flexcomm_spi_peripheral_interface.c
                src/bootloader/src/usb_hid_msc_peripheral_interface.c
                src/memory/src/sram_init_lpc.c
                src/memory/src/spifi_nor_memory.h
                src/memory/src/spifi_nor_memory.c
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_include(
        INCLUDES targets/LPC54018/src
                 src/memory/src
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.LPC54S018M_startup)
    mcux_component_version(2.7.0)
    mcux_add_source(
        SOURCES ../../devices/LPC/LPC54000/LPC54S018M/system_LPC54S018M.h
                targets/LPC54S018M/src/startup/system_LPC54S018M.c
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES targets/LPC54S018M/src/startup/iar/startup_LPC54S018M.s
        TOOLCHAINS iar
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES targets/LPC54S018M/src/startup/gcc/startup_LPC54S018M.S
        TOOLCHAINS mcux armgcc
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES src/startup/crt0.s
        TOOLCHAINS iar
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES src/startup/crt0_gcc.S
        TOOLCHAINS mcux armgcc
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES targets/LPC54S018M/src/startup/arm/startup_LPC54S018M.S
        TOOLCHAINS mdk
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_include(
        INCLUDES ../../devices/LPC54S018M
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.LPC54S018M_sources)
    mcux_component_version(2.7.0)
    mcux_add_source(
        SOURCES targets/LPC54S018M/src/bootloader_config.h
                targets/LPC54S018M/src/bl_clock_config_LPC54S018M.c
                targets/LPC54S018M/src/hardware_init_LPC54S018M.c
                targets/LPC54S018M/src/memory_map_LPC54S018M.c
                targets/LPC54S018M/src/external_memory_property_map_LPC54S018M.c
                targets/LPC54S018M/src/bl_peripherals_LPC54S018M.c
                targets/LPC54S018M/src/peripherals_pinmux.h
                targets/LPC54S018M/src/target_config.h
                targets/LPC54S018M/src/usb_device_config.h
                targets/common/src/pinmux_utility_lpc.c
                targets/common/src/bl_flexcomm_usart_irq_config_common.c
                targets/common/src/bl_flexcomm_i2c_irq_config_common.c
                targets/common/src/bl_flexcomm_spi_irq_config_common.c
                src/bootloader/src/flexcomm_usart_peripheral_interface.c
                src/bootloader/src/flexcomm_i2c_peripheral_interface.c
                src/bootloader/src/flexcomm_spi_peripheral_interface.c
                src/bootloader/src/usb_hid_msc_peripheral_interface.c
                src/memory/src/sram_init_lpc.c
                src/memory/src/spifi_nor_memory.h
                src/memory/src/spifi_nor_memory.c
                src/authentication/key_store.c
                src/authentication/key_store_hal_lpc54s018.c
                src/authentication/key_store.h
                src/authentication/key_store_hal.h
                src/authentication/skboot_common.h
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_include(
        INCLUDES targets/LPC54S018M/src
                 src/memory/src
                 src/authentication
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.LPC54S018_startup)
    mcux_component_version(2.7.0)
    mcux_add_source(
        SOURCES ../../devices/LPC/LPC54000/LPC54S018/system_LPC54S018.h
                targets/LPC54S018/src/startup/system_LPC54S018.c
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES targets/LPC54S018/src/startup/iar/startup_LPC54S018.s
        TOOLCHAINS iar
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES targets/LPC54S018/src/startup/gcc/startup_LPC54S018.S
        TOOLCHAINS mcux armgcc
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES src/startup/crt0.s
        TOOLCHAINS iar
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES src/startup/crt0_gcc.S
        TOOLCHAINS mcux armgcc
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES targets/LPC54S018/src/startup/arm/startup_LPC54S018.S
        TOOLCHAINS mdk
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_include(
        INCLUDES ../../devices/LPC54S018
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.LPC54S018_sources)
    mcux_component_version(2.7.0)
    mcux_add_source(
        SOURCES targets/LPC54S018/src/bootloader_config.h
                targets/LPC54S018/src/bl_clock_config_LPC54S018.c
                targets/LPC54S018/src/hardware_init_LPC54S018.c
                targets/LPC54S018/src/memory_map_LPC54S018.c
                targets/LPC54S018/src/external_memory_property_map_LPC54S018.c
                targets/LPC54S018/src/bl_peripherals_LPC54S018.c
                targets/LPC54S018/src/peripherals_pinmux.h
                targets/LPC54S018/src/target_config.h
                targets/LPC54S018/src/usb_device_config.h
                targets/common/src/pinmux_utility_lpc.c
                targets/common/src/bl_flexcomm_usart_irq_config_common.c
                targets/common/src/bl_flexcomm_i2c_irq_config_common.c
                targets/common/src/bl_flexcomm_spi_irq_config_common.c
                src/bootloader/src/flexcomm_usart_peripheral_interface.c
                src/bootloader/src/flexcomm_i2c_peripheral_interface.c
                src/bootloader/src/flexcomm_spi_peripheral_interface.c
                src/bootloader/src/usb_hid_msc_peripheral_interface.c
                src/memory/src/sram_init_lpc.c
                src/memory/src/spifi_nor_memory.h
                src/memory/src/spifi_nor_memory.c
                src/authentication/key_store.c
                src/authentication/key_store_hal_lpc54s018.c
                src/authentication/key_store.h
                src/authentication/key_store_hal.h
                src/authentication/skboot_common.h
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_include(
        INCLUDES targets/LPC54S018/src
                 src/memory/src
                 src/authentication
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.MIMXRT1152_startup)
    mcux_component_version(2.7.0)
    mcux_add_source(
        SOURCES ../../devices/RT/RT1150/MIMXRT1152/system_MIMXRT1152.h
        CORES cm7f
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES targets/MIMXRT1152/src/startup/system_MIMXRT1152.c
        CORES cm7f
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES targets/MIMXRT1152/src/startup/iar/startup_MIMXRT1152.s
        TOOLCHAINS iar
        CORES cm7f
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES targets/MIMXRT1152/src/startup/gcc/startup_MIMXRT1152.S
        TOOLCHAINS mcux armgcc
        CORES cm7f
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES src/startup/crt0_gcc.S
        TOOLCHAINS mcux armgcc
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_source(
        SOURCES targets/MIMXRT1152/src/startup/arm/startup_MIMXRT1152.S
        TOOLCHAINS mdk
        CORES cm7f
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_include(
        INCLUDES ../../devices/MIMXRT1152
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
endif()

if(CONFIG_MCUX_COMPONENT_middleware.mcu-boot.MIMXRT1152_sources)
    mcux_component_version(2.7.0)
    mcux_add_source(
        SOURCES targets/MIMXRT1152/src/bl_lpuart_irq_config_MIMXRT1152.c
                targets/MIMXRT1152/src/bl_mpu.h
                targets/MIMXRT1152/src/bootloader_config.h
                targets/MIMXRT1152/src/clock_cfg_MIMXRT1152.c
                targets/MIMXRT1152/src/external_memory_property_map_MIMXRT1152.c
                targets/MIMXRT1152/src/flexspi_config_MIMXRT1152.c
                targets/MIMXRT1152/src/flexspi_nand_config_MIMXRT1152.c
                targets/MIMXRT1152/src/flexspi_nor_config_MIMXRT1152.c
                targets/MIMXRT1152/src/fusemap.h
                targets/MIMXRT1152/src/hardware_init_MIMXRT1152.c
                targets/MIMXRT1152/src/memory_config.h
                targets/MIMXRT1152/src/memory_map_MIMXRT1152.c
                targets/MIMXRT1152/src/ocotp_MIMXRT1152.c
                targets/MIMXRT1152/src/periph_MIMXRT1152.c
                targets/MIMXRT1152/src/peripherals_pinmux.h
                targets/MIMXRT1152/src/sdmmc_config_MIMXRT1152.c
                targets/MIMXRT1152/src/sdmmc_convert_MIMXRT1152.c
                targets/MIMXRT1152/src/sdmmc_init.h
                targets/MIMXRT1152/src/security_config_MIMXRT1152.c
                targets/MIMXRT1152/src/semc_nand_config_MIMXRT1152.c
                targets/MIMXRT1152/src/target_config.h
                targets/common/src/pinmux_utility_imxrt_series.c
                targets/MIMXRT1152/src/usb_device_config.h
                targets/MIMXRT1152/src/sram_init_MIMXRT1152.c
                src/bootloader/src/lpuart_peripheral_interface.c
                src/bootloader/src/usb_hid_msc_peripheral_interface.c
                src/property/src/property_imx.c
                src/security/keyblob/src/keyblob_caam.c
                src/security/keyblob/src/keyblob.c
                src/security/keyblob/keyblob.h
                src/bootloader/bl_keyblob.h
                src/authentication/key_store_puf.c
                src/authentication/key_store_puf.h
                src/memory/src/semc_nand_memory.c
                src/memory/src/semc_nand_memory.h
                src/drivers/nand_ecc/nand_ecc.c
                src/drivers/nand_ecc/nand_ecc.h
                src/drivers/semc/bl_semc.c
                src/drivers/semc/bl_semc.h
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
    mcux_add_include(
        INCLUDES targets/MIMXRT1152/src
                 src
                 src/bootloader
                 src/include
                 src/startup
                 src/memory
                 src/memory/src
                 src/property
                 src/authentication
                 src/security/keyblob
                 src/drivers
                 src/drivers/flexspi_nor
                 src/drivers/flexspi
                 src/drivers/serial_nor_eeprom
                 src/drivers/sdmmc/inc
                 src/drivers/semc
                 src/drivers/nand_ecc
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/
    )
endif()

if(CONFIG_MCUX_PRJSEG_middleware.mcu-boot.MK22F51212_application_0x0000_linker)
    mcux_add_iar_linker_script(
        TARGETS release debug
        BASE_PATH ${SdkRootDirPath}
        LINKER middleware/mcu_bootloader/targets/common/linker/iar/MK22F51212/MK22FN512xxx12_application_0x0000.icf
    )
    mcux_add_mdk_linker_script(
        TARGETS release debug
        BASE_PATH ${SdkRootDirPath}
        LINKER middleware/mcu_bootloader/targets/common/linker/arm/MK22F51212/MK22FN512xxx12_application_0x0000.scf
    )
    mcux_add_armgcc_linker_script(
        TARGETS release debug
        BASE_PATH ${SdkRootDirPath}
        LINKER middleware/mcu_bootloader/targets/common/linker/gcc/MK22F51212/MK22FN512xxx12_application_0x0000.ld
    )
endif()

if(CONFIG_MCUX_PRJSEG_middleware.mcu-boot.MK22F51212_application_0xA000_linker)
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/iar/MK22F51212/MK22FN512xxx12_application_0xA000.icf
        TOOLCHAINS iar
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/arm/MK22F51212/MK22FN512xxx12_application_0xa000.scf
        TOOLCHAINS mdk
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/mcuxpresso/MK22F51212/MK22FN512xxx12_application_0xa000.ld
        TOOLCHAINS mcux
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/gcc/MK22F51212/MK22FN512xxx12_application_0xa000.ld
        TOOLCHAINS armgcc
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
endif()

if(CONFIG_MCUX_PRJSEG_middleware.mcu-boot.MK22F51212_ram_flashloader_linker)
    mcux_add_iar_linker_script(
        TARGETS release debug
        BASE_PATH ${SdkRootDirPath}
        LINKER middleware/mcu_bootloader/targets/common/linker/iar/MK22F51212/MK22FN512xxx12_ram_flashloader.icf
    )
    mcux_add_mdk_linker_script(
        TARGETS release debug
        BASE_PATH ${SdkRootDirPath}
        LINKER middleware/mcu_bootloader/targets/common/linker/arm/MK22F51212/MK22FN512xxx12_ram_flashloader.scf
    )
    mcux_add_armgcc_linker_script(
        TARGETS release debug
        BASE_PATH ${SdkRootDirPath}
        LINKER middleware/mcu_bootloader/targets/common/linker/gcc/MK22F51212/MK22FN512xxx12_ram_flashloader.ld
    )
endif()

if(CONFIG_MCUX_PRJSEG_middleware.mcu-boot.MK22F51212_flashloader_loader_linker)
    mcux_add_iar_linker_script(
        TARGETS release debug
        BASE_PATH ${SdkRootDirPath}
        LINKER middleware/mcu_bootloader/targets/common/linker/iar/MK22F51212/MK22FN512xxx12_flashloader_loader.icf
    )
    mcux_add_mdk_linker_script(
        TARGETS release debug
        BASE_PATH ${SdkRootDirPath}
        LINKER middleware/mcu_bootloader/targets/common/linker/arm/MK22F51212/MK22FN512xxx12_flashloader_loader.scf
    )
    mcux_add_armgcc_linker_script(
        TARGETS release debug
        BASE_PATH ${SdkRootDirPath}
        LINKER middleware/mcu_bootloader/targets/common/linker/gcc/MK22F51212/MK22FN512xxx12_flashloader_loader.ld
    )
endif()

if(CONFIG_MCUX_PRJSEG_middleware.mcu-boot.MK64F12_application_0x0000_linker)
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/iar/MK64F12/MK64FN1M0xxx12_application_0x0000.icf
        TOOLCHAINS iar
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/arm/MK64F12/MK64FN1M0xxx12_application_0x0000.scf
        TOOLCHAINS mdk
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/mcuxpresso/MK64F12/MK64FN1M0xxx12_application_0x0000.ld
        TOOLCHAINS mcux
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/gcc/MK64F12/MK64FN1M0xxx12_application_0x0000.ld
        TOOLCHAINS armgcc
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
endif()

if(CONFIG_MCUX_PRJSEG_middleware.mcu-boot.MK64F12_application_0xA000_linker)
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/iar/MK64F12/MK64FN1M0xxx12_application_0xA000.icf
        TOOLCHAINS iar
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/arm/MK64F12/MK64FN1M0xxx12_application_0xa000.scf
        TOOLCHAINS mdk
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/mcuxpresso/MK64F12/MK64FN1M0xxx12_application_0xa000.ld
        TOOLCHAINS mcux
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/gcc/MK64F12/MK64FN1M0xxx12_application_0xa000.ld
        TOOLCHAINS armgcc
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
endif()

if(CONFIG_MCUX_PRJSEG_middleware.mcu-boot.MK64F12_ram_flashloader_linker)
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/iar/MK64F12/MK64FN1M0xxx12_ram_flashloader.icf
        TOOLCHAINS iar
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/arm/MK64F12/MK64FN1M0xxx12_ram_flashloader.scf
        TOOLCHAINS mdk
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/mcuxpresso/MK64F12/MK64FN1M0xxx12_ram_flashloader.ld
        TOOLCHAINS mcux
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/gcc/MK64F12/MK64FN1M0xxx12_ram_flashloader.ld
        TOOLCHAINS armgcc
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
endif()

if(CONFIG_MCUX_PRJSEG_middleware.mcu-boot.MK64F12_flashloader_loader_linker)
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/iar/MK64F12/MK64FN1M0xxx12_flashloader_loader.icf
        TOOLCHAINS iar
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/arm/MK64F12/MK64FN1M0xxx12_flashloader_loader.scf
        TOOLCHAINS mdk
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/mcuxpresso/MK64F12/MK64FN1M0xxx12_flashloader_loader.ld
        TOOLCHAINS mcux
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/gcc/MK64F12/MK64FN1M0xxx12_flashloader_loader.ld
        TOOLCHAINS armgcc
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
endif()

if(CONFIG_MCUX_PRJSEG_middleware.mcu-boot.MK65F18_application_0x0000_linker)
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/iar/MK65F18/MK65FN2M0xxx18_application_0x0000.icf
        TOOLCHAINS iar
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/arm/MK65F18/MK65FN2M0xxx18_application_0x0000.scf
        TOOLCHAINS mdk
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/mcuxpresso/MK65F18/MK65FN2M0xxx18_application_0x0000.ld
        TOOLCHAINS mcux
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/gcc/MK65F18/MK65FN2M0xxx18_application_0x0000.ld
        TOOLCHAINS armgcc
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
endif()

if(CONFIG_MCUX_PRJSEG_middleware.mcu-boot.MK65F18_application_0xA000_linker)
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/iar/MK65F18/MK65FN2M0xxx18_application_0xA000.icf
        TOOLCHAINS iar
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/arm/MK65F18/MK65FN2M0xxx18_application_0xa000.scf
        TOOLCHAINS mdk
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/mcuxpresso/MK65F18/MK65FN2M0xxx18_application_0xa000.ld
        TOOLCHAINS mcux
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/gcc/MK65F18/MK65FN2M0xxx18_application_0xa000.ld
        TOOLCHAINS armgcc
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
endif()

if(CONFIG_MCUX_PRJSEG_middleware.mcu-boot.MK65F18_ram_flashloader_linker)
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/iar/MK65F18/MK65FN2M0xxx18_ram_flashloader.icf
        TOOLCHAINS iar
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/arm/MK65F18/MK65FN2M0xxx18_ram_flashloader.scf
        TOOLCHAINS mdk
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/mcuxpresso/MK65F18/MK65FN2M0xxx18_ram_flashloader.ld
        TOOLCHAINS mcux
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/gcc/MK65F18/MK65FN2M0xxx18_ram_flashloader.ld
        TOOLCHAINS armgcc
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
endif()

if(CONFIG_MCUX_PRJSEG_middleware.mcu-boot.MK65F18_flashloader_loader_linker)
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/iar/MK65F18/MK65FN2M0xxx18_flashloader_loader.icf
        TOOLCHAINS iar
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/arm/MK65F18/MK65FN2M0xxx18_flashloader_loader.scf
        TOOLCHAINS mdk
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/mcuxpresso/MK65F18/MK65FN2M0xxx18_flashloader_loader.ld
        TOOLCHAINS mcux
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/gcc/MK65F18/MK65FN2M0xxx18_flashloader_loader.ld
        TOOLCHAINS armgcc
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
endif()

if(CONFIG_MCUX_PRJSEG_middleware.mcu-boot.MK66F18_application_0x0000_linker)
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/iar/MK66F18/MK66FN2M0xxx18_application_0x0000.icf
        TOOLCHAINS iar
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/arm/MK66F18/MK66FN2M0xxx18_application_0x0000.scf
        TOOLCHAINS mdk
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/mcuxpresso/MK66F18/MK66FN2M0xxx18_application_0x0000.ld
        TOOLCHAINS mcux
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/gcc/MK66F18/MK66FN2M0xxx18_application_0x0000.ld
        TOOLCHAINS armgcc
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
endif()

if(CONFIG_MCUX_PRJSEG_middleware.mcu-boot.MK66F18_application_0xA000_linker)
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/iar/MK66F18/MK66FN2M0xxx18_application_0xA000.icf
        TOOLCHAINS iar
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/arm/MK66F18/MK66FN2M0xxx18_application_0xa000.scf
        TOOLCHAINS mdk
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/mcuxpresso/MK66F18/MK66FN2M0xxx18_application_0xa000.ld
        TOOLCHAINS mcux
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/gcc/MK66F18/MK66FN2M0xxx18_application_0xa000.ld
        TOOLCHAINS armgcc
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
endif()

if(CONFIG_MCUX_PRJSEG_middleware.mcu-boot.MK66F18_ram_flashloader_linker)
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/iar/MK66F18/MK66FN2M0xxx18_ram_flashloader.icf
        TOOLCHAINS iar
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/arm/MK66F18/MK66FN2M0xxx18_ram_flashloader.scf
        TOOLCHAINS mdk
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/mcuxpresso/MK66F18/MK66FN2M0xxx18_ram_flashloader.ld
        TOOLCHAINS mcux
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/gcc/MK66F18/MK66FN2M0xxx18_ram_flashloader.ld
        TOOLCHAINS armgcc
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
endif()

if(CONFIG_MCUX_PRJSEG_middleware.mcu-boot.MK66F18_flashloader_loader_linker)
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/iar/MK66F18/MK66FN2M0xxx18_flashloader_loader.icf
        TOOLCHAINS iar
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/arm/MK66F18/MK66FN2M0xxx18_flashloader_loader.scf
        TOOLCHAINS mdk
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/mcuxpresso/MK66F18/MK66FN2M0xxx18_flashloader_loader.ld
        TOOLCHAINS mcux
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/gcc/MK66F18/MK66FN2M0xxx18_flashloader_loader.ld
        TOOLCHAINS armgcc
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
endif()

if(CONFIG_MCUX_PRJSEG_middleware.mcu-boot.MK80F25615_application_0x0000_linker)
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/iar/MK80F25615/MK80FN256xxx15_application_0x0000.icf
        TOOLCHAINS iar
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/arm/MK80F25615/MK80FN256xxx15_application_0x0000.scf
        TOOLCHAINS mdk
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/mcuxpresso/MK80F25615/MK80FN256xxx15_application_0x0000.ld
        TOOLCHAINS mcux
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/gcc/MK80F25615/MK80FN256xxx15_application_0x0000.ld
        TOOLCHAINS armgcc
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
endif()

if(CONFIG_MCUX_PRJSEG_middleware.mcu-boot.MK80F25615_application_0xA000_linker)
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/iar/MK80F25615/MK80FN256xxx15_application_0xA000.icf
        TOOLCHAINS iar
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/arm/MK80F25615/MK80FN256xxx15_application_0xa000.scf
        TOOLCHAINS mdk
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/mcuxpresso/MK80F25615/MK80FN256xxx15_application_0xa000.ld
        TOOLCHAINS mcux
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/gcc/MK80F25615/MK80FN256xxx15_application_0xa000.ld
        TOOLCHAINS armgcc
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
endif()

if(CONFIG_MCUX_PRJSEG_middleware.mcu-boot.MK80F25615_flash_a000_linker)
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/apps/demo_qspi/led_demo/targets/common/linker/MK80F25615/iar/MK80FN256xxx15_flash_a000.icf
                middleware/mcu_bootloader/apps/demo_qspi/led_demo/targets/common/linker/MK80F25615/arm/MK80FN256xxx15_flash_a000.scf
                middleware/mcu_bootloader/apps/demo_qspi/led_demo/targets/common/linker/MK80F25615/mcuxpresso/MK80FN256xxx15_flash_a000.ld
                middleware/mcu_bootloader/apps/demo_qspi/led_demo/targets/common/linker/MK80F25615/gcc/MK80FN256xxx15_flash_a000.ld
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
endif()

if(CONFIG_MCUX_PRJSEG_middleware.mcu-boot.MK80F25615_qspi_a000_linker)
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/apps/demo_qspi/led_demo/targets/common/linker/MK80F25615/iar/MK80FN256xxx15_qspi_a000.icf
                middleware/mcu_bootloader/apps/demo_qspi/led_demo/targets/common/linker/MK80F25615/arm/MK80FN256xxx15_qspi_a000.scf
                middleware/mcu_bootloader/apps/demo_qspi/led_demo/targets/common/linker/MK80F25615/mcuxpresso/MK80FN256xxx15_qspi_a000.ld
                middleware/mcu_bootloader/apps/demo_qspi/led_demo/targets/common/linker/MK80F25615/gcc/MK80FN256xxx15_qspi_a000.ld
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
endif()

if(CONFIG_MCUX_PRJSEG_middleware.mcu-boot.MK80F25615_qspi_alias_a000_linker)
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/apps/demo_qspi/led_demo/targets/common/linker/MK80F25615/iar/MK80FN256xxx15_qspi_alias_a000.icf
                middleware/mcu_bootloader/apps/demo_qspi/led_demo/targets/common/linker/MK80F25615/arm/MK80FN256xxx15_qspi_alias_a000.scf
                middleware/mcu_bootloader/apps/demo_qspi/led_demo/targets/common/linker/MK80F25615/mcuxpresso/MK80FN256xxx15_qspi_alias_a000.ld
                middleware/mcu_bootloader/apps/demo_qspi/led_demo/targets/common/linker/MK80F25615/gcc/MK80FN256xxx15_qspi_alias_a000.ld
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
endif()

if(CONFIG_MCUX_PRJSEG_middleware.mcu-boot.MK82F25615_application_0x0000_linker)
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/iar/MK82F25615/MK82FN256xxx15_application_0x0000.icf
        TOOLCHAINS iar
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/arm/MK82F25615/MK82FN256xxx15_application_0x0000.scf
        TOOLCHAINS mdk
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/mcuxpresso/MK82F25615/MK82FN256xxx15_application_0x0000.ld
        TOOLCHAINS mcux
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/gcc/MK82F25615/MK82FN256xxx15_application_0x0000.ld
        TOOLCHAINS armgcc
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
endif()

if(CONFIG_MCUX_PRJSEG_middleware.mcu-boot.MK82F25615_application_0xA000_linker)
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/iar/MK82F25615/MK82FN256xxx15_application_0xA000.icf
        TOOLCHAINS iar
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/arm/MK82F25615/MK82FN256xxx15_application_0xa000.scf
        TOOLCHAINS mdk
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/mcuxpresso/MK82F25615/MK82FN256xxx15_application_0xa000.ld
        TOOLCHAINS mcux
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/gcc/MK82F25615/MK82FN256xxx15_application_0xa000.ld
        TOOLCHAINS armgcc
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
endif()

if(CONFIG_MCUX_PRJSEG_middleware.mcu-boot.MK82F25615_flash_a000_linker)
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/apps/demo_qspi/led_demo/targets/common/linker/MK82F25615/iar/MK82FN256xxx15_flash_a000.icf
                middleware/mcu_bootloader/apps/demo_qspi/led_demo/targets/common/linker/MK82F25615/arm/MK82FN256xxx15_flash_a000.scf
                middleware/mcu_bootloader/apps/demo_qspi/led_demo/targets/common/linker/MK82F25615/mcuxpresso/MK82FN256xxx15_flash_a000.ld
                middleware/mcu_bootloader/apps/demo_qspi/led_demo/targets/common/linker/MK82F25615/gcc/MK82FN256xxx15_flash_a000.ld
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
endif()

if(CONFIG_MCUX_PRJSEG_middleware.mcu-boot.MK82F25615_qspi_a000_linker)
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/apps/demo_qspi/led_demo/targets/common/linker/MK82F25615/iar/MK82FN256xxx15_qspi_a000.icf
                middleware/mcu_bootloader/apps/demo_qspi/led_demo/targets/common/linker/MK82F25615/arm/MK82FN256xxx15_qspi_a000.scf
                middleware/mcu_bootloader/apps/demo_qspi/led_demo/targets/common/linker/MK82F25615/mcuxpresso/MK82FN256xxx15_qspi_a000.ld
                middleware/mcu_bootloader/apps/demo_qspi/led_demo/targets/common/linker/MK82F25615/gcc/MK82FN256xxx15_qspi_a000.ld
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
endif()

if(CONFIG_MCUX_PRJSEG_middleware.mcu-boot.MK82F25615_qspi_alias_a000_linker)
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/apps/demo_qspi/led_demo/targets/common/linker/MK82F25615/iar/MK82FN256xxx15_qspi_alias_a000.icf
                middleware/mcu_bootloader/apps/demo_qspi/led_demo/targets/common/linker/MK82F25615/arm/MK82FN256xxx15_qspi_alias_a000.scf
                middleware/mcu_bootloader/apps/demo_qspi/led_demo/targets/common/linker/MK82F25615/mcuxpresso/MK82FN256xxx15_qspi_alias_a000.ld
                middleware/mcu_bootloader/apps/demo_qspi/led_demo/targets/common/linker/MK82F25615/gcc/MK82FN256xxx15_qspi_alias_a000.ld
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
endif()

if(CONFIG_MCUX_PRJSEG_middleware.mcu-boot.MKV11Z7_application_0x0000_linker)
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/iar/MKV11Z7/MKV11Z128xxx7_application_0x0000.icf
        TOOLCHAINS iar
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/arm/MKV11Z7/MKV11Z128xxx7_application_0x0000.scf
        TOOLCHAINS mdk
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/mcuxpresso/MKV11Z7/MKV11Z128xxx7_application_0x0000.ld
        TOOLCHAINS mcux
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/gcc/MKV11Z7/MKV11Z128xxx7_application_0x0000.ld
        TOOLCHAINS armgcc
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
endif()

if(CONFIG_MCUX_PRJSEG_middleware.mcu-boot.MKV11Z7_application_0xA000_linker)
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/iar/MKV11Z7/MKV11Z128xxx7_application_0xA000.icf
        TOOLCHAINS iar
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/arm/MKV11Z7/MKV11Z128xxx7_application_0xa000.scf
        TOOLCHAINS mdk
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/mcuxpresso/MKV11Z7/MKV11Z128xxx7_application_0xa000.ld
        TOOLCHAINS mcux
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/gcc/MKV11Z7/MKV11Z128xxx7_application_0xa000.ld
        TOOLCHAINS armgcc
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
endif()

if(CONFIG_MCUX_PRJSEG_middleware.mcu-boot.MKV11Z7_ram_flashloader_linker)
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/iar/MKV11Z7/MKV11Z128xxx7_ram_flashloader.icf
        TOOLCHAINS iar
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/arm/MKV11Z7/MKV11Z128xxx7_ram_flashloader.scf
        TOOLCHAINS mdk
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/mcuxpresso/MKV11Z7/MKV11Z128xxx7_ram_flashloader.ld
        TOOLCHAINS mcux
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/gcc/MKV11Z7/MKV11Z128xxx7_ram_flashloader.ld
        TOOLCHAINS armgcc
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
endif()

if(CONFIG_MCUX_PRJSEG_middleware.mcu-boot.MKV11Z7_flashloader_loader_linker)
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/iar/MKV11Z7/MKV11Z128xxx7_flashloader_loader.icf
        TOOLCHAINS iar
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/arm/MKV11Z7/MKV11Z128xxx7_flashloader_loader.scf
        TOOLCHAINS mdk
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/mcuxpresso/MKV11Z7/MKV11Z128xxx7_flashloader_loader.ld
        TOOLCHAINS mcux
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/gcc/MKV11Z7/MKV11Z128xxx7_flashloader_loader.ld
        TOOLCHAINS armgcc
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
endif()

if(CONFIG_MCUX_PRJSEG_middleware.mcu-boot.MKV31F51212_application_0x0000_linker)
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/iar/MKV31F51212/MKV31F512xxx12_application_0x0000.icf
        TOOLCHAINS iar
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/arm/MKV31F51212/MKV31F512xxx12_application_0x0000.scf
        TOOLCHAINS mdk
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/mcuxpresso/MKV31F51212/MKV31F512xxx12_application_0x0000.ld
        TOOLCHAINS mcux
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/gcc/MKV31F51212/MKV31F512xxx12_application_0x0000.ld
        TOOLCHAINS armgcc
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
endif()

if(CONFIG_MCUX_PRJSEG_middleware.mcu-boot.MKV31F51212_application_0xA000_linker)
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/iar/MKV31F51212/MKV31F512xxx12_application_0xA000.icf
        TOOLCHAINS iar
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/arm/MKV31F51212/MKV31F512xxx12_application_0xa000.scf
        TOOLCHAINS mdk
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/mcuxpresso/MKV31F51212/MKV31F512xxx12_application_0xa000.ld
        TOOLCHAINS mcux
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/gcc/MKV31F51212/MKV31F512xxx12_application_0xa000.ld
        TOOLCHAINS armgcc
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
endif()

if(CONFIG_MCUX_PRJSEG_middleware.mcu-boot.MKV31F51212_ram_flashloader_linker)
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/iar/MKV31F51212/MKV31F512xxx12_ram_flashloader.icf
        TOOLCHAINS iar
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/arm/MKV31F51212/MKV31F512xxx12_ram_flashloader.scf
        TOOLCHAINS mdk
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/mcuxpresso/MKV31F51212/MKV31F512xxx12_ram_flashloader.ld
        TOOLCHAINS mcux
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/gcc/MKV31F51212/MKV31F512xxx12_ram_flashloader.ld
        TOOLCHAINS armgcc
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
endif()

if(CONFIG_MCUX_PRJSEG_middleware.mcu-boot.MKV31F51212_flashloader_loader_linker)
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/iar/MKV31F51212/MKV31F512xxx12_flashloader_loader.icf
        TOOLCHAINS iar
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/arm/MKV31F51212/MKV31F512xxx12_flashloader_loader.scf
        TOOLCHAINS mdk
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/mcuxpresso/MKV31F51212/MKV31F512xxx12_flashloader_loader.ld
        TOOLCHAINS mcux
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/gcc/MKV31F51212/MKV31F512xxx12_flashloader_loader.ld
        TOOLCHAINS armgcc
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
endif()

if(CONFIG_MCUX_PRJSEG_middleware.mcu-boot.MKV46F16_application_0xA000_linker)
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/iar/MKV46F16/MKV46F256xxx16_application_0xA000.icf
        TOOLCHAINS iar
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/arm/MKV46F16/MKV46F256xxx16_application_0xa000.scf
        TOOLCHAINS mdk
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/mcuxpresso/MKV46F16/MKV46F256xxx16_application_0xa000.ld
        TOOLCHAINS mcux
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/gcc/MKV46F16/MKV46F256xxx16_application_0xa000.ld
        TOOLCHAINS armgcc
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
endif()

if(CONFIG_MCUX_PRJSEG_middleware.mcu-boot.MKV46F16_ram_flashloader_linker)
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/iar/MKV46F16/MKV46F256xxx16_ram_flashloader.icf
        TOOLCHAINS iar
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/arm/MKV46F16/MKV46F256xxx16_ram_flashloader.scf
        TOOLCHAINS mdk
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/mcuxpresso/MKV46F16/MKV46F256xxx16_ram_flashloader.ld
        TOOLCHAINS mcux
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/gcc/MKV46F16/MKV46F256xxx16_ram_flashloader.ld
        TOOLCHAINS armgcc
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
endif()

if(CONFIG_MCUX_PRJSEG_middleware.mcu-boot.MKV46F16_flashloader_loader_linker)
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/iar/MKV46F16/MKV46F256xxx16_flashloader_loader.icf
        TOOLCHAINS iar
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/arm/MKV46F16/MKV46F256xxx16_flashloader_loader.scf
        TOOLCHAINS mdk
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/mcuxpresso/MKV46F16/MKV46F256xxx16_flashloader_loader.ld
        TOOLCHAINS mcux
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/gcc/MKV46F16/MKV46F256xxx16_flashloader_loader.ld
        TOOLCHAINS armgcc
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
endif()

if(CONFIG_MCUX_PRJSEG_middleware.mcu-boot.MKV58F24_application_0x10000000_linker)
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/iar/MKV58F24/MKV58F1M0xxx24_application_0x10000000.icf
        TOOLCHAINS iar
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/arm/MKV58F24/MKV58F1M0xxx24_application_0x10000000.scf
        TOOLCHAINS mdk
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/mcuxpresso/MKV58F24/MKV58F1M0xxx24_application_0x10000000.ld
        TOOLCHAINS mcux
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/gcc/MKV58F24/MKV58F1M0xxx24_application_0x10000000.ld
        TOOLCHAINS armgcc
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
endif()

if(CONFIG_MCUX_PRJSEG_middleware.mcu-boot.MKV58F24_application_0x1000a000_linker)
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/iar/MKV58F24/MKV58F1M0xxx24_application_0x1000A000.icf
        TOOLCHAINS iar
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/arm/MKV58F24/MKV58F1M0xxx24_application_0x1000a000.scf
        TOOLCHAINS mdk
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/mcuxpresso/MKV58F24/MKV58F1M0xxx24_application_0x1000a000.ld
        TOOLCHAINS mcux
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/gcc/MKV58F24/MKV58F1M0xxx24_application_0x1000a000.ld
        TOOLCHAINS armgcc
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
endif()

if(CONFIG_MCUX_PRJSEG_middleware.mcu-boot.MKV58F24_ram_flashloader_linker)
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/iar/MKV58F24/MKV58F1M0xxx24_ram_flashloader.icf
        TOOLCHAINS iar
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/arm/MKV58F24/MKV58F1M0xxx24_ram_flashloader.scf
        TOOLCHAINS mdk
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/mcuxpresso/MKV58F24/MKV58F1M0xxx24_ram_flashloader.ld
        TOOLCHAINS mcux
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/gcc/MKV58F24/MKV58F1M0xxx24_ram_flashloader.ld
        TOOLCHAINS armgcc
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
endif()

if(CONFIG_MCUX_PRJSEG_middleware.mcu-boot.MKV58F24_flashloader_loader_linker)
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/iar/MKV58F24/MKV58F1M0xxx24_flashloader_loader.icf
        TOOLCHAINS iar
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/arm/MKV58F24/MKV58F1M0xxx24_flashloader_loader.scf
        TOOLCHAINS mdk
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/mcuxpresso/MKV58F24/MKV58F1M0xxx24_flashloader_loader.ld
        TOOLCHAINS mcux
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/gcc/MKV58F24/MKV58F1M0xxx24_flashloader_loader.ld
        TOOLCHAINS armgcc
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
endif()

if(CONFIG_MCUX_PRJSEG_middleware.mcu-boot.K32L2A41A_application_0x0000_linker)
    mcux_add_iar_linker_script(
        TARGETS release debug
        BASE_PATH ${SdkRootDirPath}
        LINKER middleware/mcu_bootloader/targets/common/linker/iar/K32L2A41A/K32L2A41xxxxA_application_0x0000.icf
    )
    mcux_add_mdk_linker_script(
        TARGETS release debug
        BASE_PATH ${SdkRootDirPath}
        LINKER middleware/mcu_bootloader/targets/common/linker/arm/K32L2A41A/K32L2A41xxxxA_application_0x0000.scf
    )
    mcux_add_armgcc_linker_script(
        TARGETS release debug
        BASE_PATH ${SdkRootDirPath}
        LINKER middleware/mcu_bootloader/targets/common/linker/gcc/K32L2A41A/K32L2A41xxxxA_application_0x0000.ld
    )
endif()

if(CONFIG_MCUX_PRJSEG_middleware.mcu-boot.K32L2A41A_application_0xA000_linker)
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/iar/K32L2A41A/K32L2A41xxxxA_application_0xA000.icf
        TOOLCHAINS iar
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/arm/K32L2A41A/K32L2A41xxxxA_application_0xa000.scf
        TOOLCHAINS mdk
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/mcuxpresso/K32L2A41A/K32L2A41xxxxA_application_0xa000.ld
        TOOLCHAINS mcux
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/gcc/K32L2A41A/K32L2A41xxxxA_application_0xa000.ld
        TOOLCHAINS armgcc
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
endif()

if(CONFIG_MCUX_PRJSEG_middleware.mcu-boot.MKM35Z7_application_0x0000_linker)
    mcux_add_iar_linker_script(
        TARGETS release debug
        BASE_PATH ${SdkRootDirPath}
        LINKER middleware/mcu_bootloader/targets/common/linker/iar/MKM35Z7/MKM35Z512xxx7_application_0x0000.icf
    )
    mcux_add_armgcc_linker_script(
        TARGETS release debug
        BASE_PATH ${SdkRootDirPath}
        LINKER middleware/mcu_bootloader/targets/common/linker/gcc/MKM35Z7/MKM35Z512xxx7_application_0x0000.ld
    )
    mcux_add_mdk_linker_script(
        TARGETS release debug
        BASE_PATH ${SdkRootDirPath}
        LINKER middleware/mcu_bootloader/targets/common/linker/arm/MKM35Z7/MKM35Z512xxx7_application_0x0000.scf
    )
endif()

if(CONFIG_MCUX_PRJSEG_middleware.mcu-boot.MKM35Z7_application_0xA000_linker)
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/iar/MKM35Z7/MKM35Z512xxx7_application_0xA000.icf
        TOOLCHAINS iar
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/arm/MKM35Z7/MKM35Z512xxx7_application_0xa000.scf
        TOOLCHAINS mdk
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/mcuxpresso/MKM35Z7/MKM35Z512xxx7_application_0xa000.ld
        TOOLCHAINS mcux
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/gcc/MKM35Z7/MKM35Z512xxx7_application_0xa000.ld
        TOOLCHAINS armgcc
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
endif()

if(CONFIG_MCUX_PRJSEG_middleware.mcu-boot.MKE16Z4_application_0x0000_linker)
    mcux_add_iar_linker_script(
        TARGETS release debug
        BASE_PATH ${SdkRootDirPath}
        LINKER middleware/mcu_bootloader/targets/common/linker/iar/MKE16Z4/MKE16Z64xxx4_application_0x0000.icf
    )
    mcux_add_armgcc_linker_script(
        TARGETS release debug
        BASE_PATH ${SdkRootDirPath}
        LINKER middleware/mcu_bootloader/targets/common/linker/gcc/MKE16Z4/MKE16Z64xxx4_application_0x0000.ld
    )
    mcux_add_mdk_linker_script(
        TARGETS release debug
        BASE_PATH ${SdkRootDirPath}
        LINKER middleware/mcu_bootloader/targets/common/linker/arm/MKE16Z4/MKE16Z64xxx4_application_0x0000.scf
    )
endif()

if(CONFIG_MCUX_PRJSEG_middleware.mcu-boot.MKE16Z4_application_0x8000_linker)
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/iar/MKE16Z4/MKE16Z64xxx4_application_0x8000.icf
        TOOLCHAINS iar
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/arm/MKE16Z4/MKE16Z64xxx4_application_0x8000.scf
        TOOLCHAINS mdk
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/mcuxpresso/MKE16Z4/MKE16Z64xxx4_application_0x8000.ld
        TOOLCHAINS mcux
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/gcc/MKE16Z4/MKE16Z64xxx4_application_0x8000.ld
        TOOLCHAINS armgcc
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
endif()

if(CONFIG_MCUX_PRJSEG_middleware.mcu-boot.MKE17Z7_application_0x0000_linker)
    mcux_add_iar_linker_script(
        TARGETS release debug
        BASE_PATH ${SdkRootDirPath}
        LINKER middleware/mcu_bootloader/targets/common/linker/iar/MKE17Z7/MKE17Z256xxx7_application_0x0000.icf
    )
    mcux_add_armgcc_linker_script(
        TARGETS release debug
        BASE_PATH ${SdkRootDirPath}
        LINKER middleware/mcu_bootloader/targets/common/linker/gcc/MKE17Z7/MKE17Z256xxx7_application_0x0000.ld
    )
    mcux_add_mdk_linker_script(
        TARGETS release debug
        BASE_PATH ${SdkRootDirPath}
        LINKER middleware/mcu_bootloader/targets/common/linker/arm/MKE17Z7/MKE17Z256xxx7_application_0x0000.scf
    )
endif()

if(CONFIG_MCUX_PRJSEG_middleware.mcu-boot.MKE17Z7_application_0xA000_linker)
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/iar/MKE17Z7/MKE17Z256xxx7_application_0xA000.icf
        TOOLCHAINS iar
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/arm/MKE17Z7/MKE17Z256xxx7_application_0xa000.scf
        TOOLCHAINS mdk
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/mcuxpresso/MKE17Z7/MKE17Z256xxx7_application_0xa000.ld
        TOOLCHAINS mcux
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/gcc/MKE17Z7/MKE17Z256xxx7_application_0xa000.ld
        TOOLCHAINS armgcc
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
endif()

if(CONFIG_MCUX_PRJSEG_middleware.mcu-boot.MKE17Z7_ram_flashloader_linker)
    mcux_add_iar_linker_script(
        TARGETS release debug
        BASE_PATH ${SdkRootDirPath}
        LINKER middleware/mcu_bootloader/targets/common/linker/iar/MKE17Z7/MKE17Z256xxx7_ram_flashloader.icf
    )
    mcux_add_armgcc_linker_script(
        TARGETS release debug
        BASE_PATH ${SdkRootDirPath}
        LINKER middleware/mcu_bootloader/targets/common/linker/gcc/MKE17Z7/MKE17Z256xxx7_ram_flashloader.ld
    )
    mcux_add_mdk_linker_script(
        TARGETS release debug
        BASE_PATH ${SdkRootDirPath}
        LINKER middleware/mcu_bootloader/targets/common/linker/arm/MKE17Z7/MKE17Z256xxx7_ram_flashloader.scf
    )
endif()

if(CONFIG_MCUX_PRJSEG_middleware.mcu-boot.MKE17Z7_flashloader_loader_linker)
    mcux_add_iar_linker_script(
        TARGETS release debug
        BASE_PATH ${SdkRootDirPath}
        LINKER middleware/mcu_bootloader/targets/common/linker/iar/MKE17Z7/MKE17Z256xxx7_flashloader_loader.icf
    )
    mcux_add_armgcc_linker_script(
        TARGETS release debug
        BASE_PATH ${SdkRootDirPath}
        LINKER middleware/mcu_bootloader/targets/common/linker/gcc/MKE17Z7/MKE17Z256xxx7_flashloader_loader.ld
    )
    mcux_add_mdk_linker_script(
        TARGETS release debug
        BASE_PATH ${SdkRootDirPath}
        LINKER middleware/mcu_bootloader/targets/common/linker/arm/MKE17Z7/MKE17Z256xxx7_flashloader_loader.scf
    )
endif()

if(CONFIG_MCUX_PRJSEG_middleware.mcu-boot.MKE17Z9_application_0x0000_linker)
    mcux_add_iar_linker_script(
        TARGETS release debug
        BASE_PATH ${SdkRootDirPath}
        LINKER middleware/mcu_bootloader/targets/common/linker/iar/MKE17Z9/MKE17Z512xxx9_application_0x0000.icf
    )
    mcux_add_armgcc_linker_script(
        TARGETS release debug
        BASE_PATH ${SdkRootDirPath}
        LINKER middleware/mcu_bootloader/targets/common/linker/gcc/MKE17Z9/MKE17Z512xxx9_application_0x0000.ld
    )
    mcux_add_mdk_linker_script(
        TARGETS release debug
        BASE_PATH ${SdkRootDirPath}
        LINKER middleware/mcu_bootloader/targets/common/linker/arm/MKE17Z9/MKE17Z512xxx9_application_0x0000.scf
    )
endif()

if(CONFIG_MCUX_PRJSEG_middleware.mcu-boot.MKE17Z9_application_0xA000_linker)
    mcux_add_iar_linker_script(
        TARGETS release debug
        BASE_PATH ${SdkRootDirPath}
        LINKER middleware/mcu_bootloader/targets/common/linker/iar/MKE17Z9/MKE17Z512xxx9_application_0xA000.icf
    )
    mcux_add_armgcc_linker_script(
        TARGETS release debug
        BASE_PATH ${SdkRootDirPath}
        LINKER middleware/mcu_bootloader/targets/common/linker/gcc/MKE17Z9/MKE17Z512xxx9_application_0xa000.ld
    )
    mcux_add_mdk_linker_script(
        TARGETS release debug
        BASE_PATH ${SdkRootDirPath}
        LINKER middleware/mcu_bootloader/targets/common/linker/arm/MKE17Z9/MKE17Z512xxx9_application_0xa000.scf
    )
endif()

if(CONFIG_MCUX_PRJSEG_middleware.mcu-boot.MKE17Z9_ram_flashloader_linker)
    mcux_add_iar_linker_script(
        TARGETS release debug
        BASE_PATH ${SdkRootDirPath}
        LINKER middleware/mcu_bootloader/targets/common/linker/iar/MKE17Z9/MKE17Z512xxx9_ram_flashloader.icf
    )
    mcux_add_armgcc_linker_script(
        TARGETS release debug
        BASE_PATH ${SdkRootDirPath}
        LINKER middleware/mcu_bootloader/targets/common/linker/gcc/MKE17Z9/MKE17Z512xxx9_ram_flashloader.ld
    )
    mcux_add_mdk_linker_script(
        TARGETS release debug
        BASE_PATH ${SdkRootDirPath}
        LINKER middleware/mcu_bootloader/targets/common/linker/arm/MKE17Z9/MKE17Z512xxx9_ram_flashloader.scf
    )
endif()

if(CONFIG_MCUX_PRJSEG_middleware.mcu-boot.MKE17Z9_flashloader_loader_linker)
    mcux_add_iar_linker_script(
        TARGETS release debug
        BASE_PATH ${SdkRootDirPath}
        LINKER middleware/mcu_bootloader/targets/common/linker/iar/MKE17Z9/MKE17Z512xxx9_flashloader_loader.icf
    )
    mcux_add_armgcc_linker_script(
        TARGETS release debug
        BASE_PATH ${SdkRootDirPath}
        LINKER middleware/mcu_bootloader/targets/common/linker/gcc/MKE17Z9/MKE17Z512xxx9_flashloader_loader.ld
    )
    mcux_add_mdk_linker_script(
        TARGETS release debug
        BASE_PATH ${SdkRootDirPath}
        LINKER middleware/mcu_bootloader/targets/common/linker/arm/MKE17Z9/MKE17Z512xxx9_flashloader_loader.scf
    )
endif()

if(CONFIG_MCUX_PRJSEG_middleware.mcu-boot.MIMXRT1052_ram_flashloader_linker)
    mcux_add_iar_linker_script(
        TARGETS release
        BASE_PATH ${SdkRootDirPath}
        LINKER middleware/mcu_bootloader/targets/common/linker/iar/MIMXRT1052/MIMXRT1052_ram_flashloader.icf
    )
    mcux_add_mdk_linker_script(
        TARGETS release
        BASE_PATH ${SdkRootDirPath}
        LINKER middleware/mcu_bootloader/targets/common/linker/arm/MIMXRT1052/MIMXRT1052_ram_flashloader.scf
    )
    # mcux_add_mcux_linker_script(
        # TARGETS release
        # BASE_PATH ${SdkRootDirPath}
        # LINKER middleware/mcu_bootloader/targets/common/linker/mcuxpresso/MIMXRT1052/MIMXRT1052_ram_flashloader.ld
    # )
    mcux_add_armgcc_linker_script(
        TARGETS release
        BASE_PATH ${SdkRootDirPath}
        LINKER middleware/mcu_bootloader/targets/common/linker/gcc/MIMXRT1052/MIMXRT1052_ram_flashloader.ld
    )
endif()

if(CONFIG_MCUX_PRJSEG_middleware.mcu-boot.MIMXRT1052_application_0xa000_linker)
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/iar/MIMXRT1052/MIMXRT1052_application_0xa000.icf
        TOOLCHAINS iar
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/arm/MIMXRT1052/MIMXRT1052_application_0xa000.scf
        TOOLCHAINS mdk
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/mcuxpresso/MIMXRT1052/MIMXRT1052_application_0xa000.ld
        TOOLCHAINS mcux
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/gcc/MIMXRT1052/MIMXRT1052_application_0xa000.ld
        TOOLCHAINS armgcc
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
endif()

if(CONFIG_MCUX_PRJSEG_middleware.mcu-boot.MIMXRT1052_application_0x60002000_linker)
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/iar/MIMXRT1052/MIMXRT1052_application_0x60002000.icf
        TOOLCHAINS iar
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/arm/MIMXRT1052/MIMXRT1052_application_0x60002000.scf
        TOOLCHAINS mdk
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/mcuxpresso/MIMXRT1052/MIMXRT1052_application_0x60002000.ld
        TOOLCHAINS mcux
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/gcc/MIMXRT1052/MIMXRT1052_application_0x60002000.ld
        TOOLCHAINS armgcc
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
endif()

if(CONFIG_MCUX_PRJSEG_middleware.mcu-boot.MIMXRT1021_ram_flashloader_linker)
    mcux_add_iar_linker_script(
        TARGETS release
        BASE_PATH ${SdkRootDirPath}
        LINKER middleware/mcu_bootloader/targets/common/linker/iar/MIMXRT1021/MIMXRT1021_ram_flashloader.icf
    )
    mcux_add_mdk_linker_script(
        TARGETS release
        BASE_PATH ${SdkRootDirPath}
        LINKER middleware/mcu_bootloader/targets/common/linker/arm/MIMXRT1021/MIMXRT1021_ram_flashloader.scf
    )
    # mcux_add_mcux_linker_script(
        # TARGETS release
        # BASE_PATH ${SdkRootDirPath}
        # LINKER middleware/mcu_bootloader/targets/common/linker/mcuxpresso/MIMXRT1021/MIMXRT1021_ram_flashloader.ld
    # )
    mcux_add_armgcc_linker_script(
        TARGETS release
        BASE_PATH ${SdkRootDirPath}
        LINKER middleware/mcu_bootloader/targets/common/linker/gcc/MIMXRT1021/MIMXRT1021_ram_flashloader.ld
    )
endif()

if(CONFIG_MCUX_PRJSEG_middleware.mcu-boot.MIMXRT1021_flash_bootloader_linker)
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/iar/MIMXRT1021/MIMXRT1021_flash_bootloader.icf
        TOOLCHAINS iar
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/arm/MIMXRT1021/MIMXRT1021_flash_bootloader.scf
        TOOLCHAINS mdk
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/mcuxpresso/MIMXRT1021/MIMXRT1021_flash_bootloader.ld
        TOOLCHAINS mcux
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/gcc/MIMXRT1021/MIMXRT1021_flash_bootloader.ld
        TOOLCHAINS armgcc
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
endif()

if(CONFIG_MCUX_PRJSEG_middleware.mcu-boot.MIMXRT1021_application_0xa000_linker)
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/iar/MIMXRT1021/MIMXRT1021_application_0xa000.icf
        TOOLCHAINS iar
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/arm/MIMXRT1021/MIMXRT1021_application_0xa000.scf
        TOOLCHAINS mdk
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/mcuxpresso/MIMXRT1021/MIMXRT1021_application_0xa000.ld
        TOOLCHAINS mcux
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
endif()

if(CONFIG_MCUX_PRJSEG_middleware.mcu-boot.MIMXRT1021_application_0x60002000_linker)
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/iar/MIMXRT1021/MIMXRT1021_application_0x60002000.icf
        TOOLCHAINS iar
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/arm/MIMXRT1021/MIMXRT1021_application_0x60002000.scf
        TOOLCHAINS mdk
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/mcuxpresso/MIMXRT1021/MIMXRT1021_application_0x60002000.ld
        TOOLCHAINS mcux
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/gcc/MIMXRT1021/MIMXRT1021_application_0x60002000.ld
        TOOLCHAINS armgcc
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
endif()

if(CONFIG_MCUX_PRJSEG_middleware.mcu-boot.MIMXRT1062_ram_flashloader_linker)
    mcux_add_iar_linker_script(
        TARGETS release
        BASE_PATH ${SdkRootDirPath}
        LINKER middleware/mcu_bootloader/targets/common/linker/iar/MIMXRT1062/MIMXRT1062_ram_flashloader.icf
    )
    mcux_add_mdk_linker_script(
        TARGETS release
        BASE_PATH ${SdkRootDirPath}
        LINKER middleware/mcu_bootloader/targets/common/linker/arm/MIMXRT1062/MIMXRT1062_ram_flashloader.scf
    )
#    mcux_add_mcux_linker_script(
#        TARGETS release
#        BASE_PATH ${SdkRootDirPath}
#        LINKER middleware/mcu_bootloader/targets/common/linker/mcuxpresso/MIMXRT1062/MIMXRT1062_ram_flashloader.ld
#    )
    mcux_add_armgcc_linker_script(
        TARGETS release
        BASE_PATH ${SdkRootDirPath}
        LINKER middleware/mcu_bootloader/targets/common/linker/gcc/MIMXRT1062/MIMXRT1062_ram_flashloader.ld
    )
endif()

if(CONFIG_MCUX_PRJSEG_middleware.mcu-boot.MIMXRT1042_ram_flashloader_linker)
    mcux_add_iar_linker_script(
        TARGETS release
        BASE_PATH ${SdkRootDirPath}
        LINKER middleware/mcu_bootloader/targets/common/linker/iar/MIMXRT1042/MIMXRT1042_ram_flashloader.icf
    )
    mcux_add_mdk_linker_script(
        TARGETS release
        BASE_PATH ${SdkRootDirPath}
        LINKER middleware/mcu_bootloader/targets/common/linker/arm/MIMXRT1042/MIMXRT1042_ram_flashloader.scf
    )
    # mcux_add_mcux_linker_script(
        # TARGETS release
        # BASE_PATH ${SdkRootDirPath}
        # LINKER middleware/mcu_bootloader/targets/common/linker/mcuxpresso/MIMXRT1042/MIMXRT1042_ram_flashloader.ld
    # )
    mcux_add_armgcc_linker_script(
        TARGETS release
        BASE_PATH ${SdkRootDirPath}
        LINKER middleware/mcu_bootloader/targets/common/linker/gcc/MIMXRT1042/MIMXRT1042_ram_flashloader.ld
    )
endif()

if(CONFIG_MCUX_PRJSEG_middleware.mcu-boot.MIMXRT1042_flash_bootloader_linker)
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/iar/MIMXRT1042/MIMXRT1042_flash_bootloader.icf
        TOOLCHAINS iar
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/arm/MIMXRT1042/MIMXRT1042_flash_bootloader.scf
        TOOLCHAINS mdk
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/mcuxpresso/MIMXRT1042/MIMXRT1042_flash_bootloader.ld
        TOOLCHAINS mcux
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/gcc/MIMXRT1042/MIMXRT1042_flash_bootloader.ld
        TOOLCHAINS armgcc
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
endif()

if(CONFIG_MCUX_PRJSEG_middleware.mcu-boot.MIMXRT1064_ram_flashloader_linker)
    mcux_add_iar_linker_script(
        TARGETS release
        BASE_PATH ${SdkRootDirPath}
        LINKER middleware/mcu_bootloader/targets/common/linker/iar/MIMXRT1064/MIMXRT1064_ram_flashloader.icf
    )
    mcux_add_mdk_linker_script(
        TARGETS release
        BASE_PATH ${SdkRootDirPath}
        LINKER middleware/mcu_bootloader/targets/common/linker/arm/MIMXRT1064/MIMXRT1064_ram_flashloader.scf
    )
    # mcux_add_mcux_linker_script(
        # TARGETS release
        # BASE_PATH ${SdkRootDirPath}
        # LINKER middleware/mcu_bootloader/targets/common/linker/mcuxpresso/MIMXRT1064/MIMXRT1064_ram_flashloader.ld
    # )
    mcux_add_armgcc_linker_script(
        TARGETS release
        BASE_PATH ${SdkRootDirPath}
        LINKER middleware/mcu_bootloader/targets/common/linker/gcc/MIMXRT1064/MIMXRT1064_ram_flashloader.ld
    )
endif()

if(CONFIG_MCUX_PRJSEG_middleware.mcu-boot.MIMXRT1015_ram_flashloader_linker)
    mcux_add_iar_linker_script(
        TARGETS release
        BASE_PATH ${SdkRootDirPath}
        LINKER middleware/mcu_bootloader/targets/common/linker/iar/MIMXRT1015/MIMXRT1015_ram_flashloader.icf
    )
    mcux_add_mdk_linker_script(
        TARGETS release
        BASE_PATH ${SdkRootDirPath}
        LINKER middleware/mcu_bootloader/targets/common/linker/arm/MIMXRT1015/MIMXRT1015_ram_flashloader.scf
    )
    # mcux_add_mcux_linker_script(
        # TARGETS release
        # BASE_PATH ${SdkRootDirPath}
        # LINKER middleware/mcu_bootloader/targets/common/linker/mcuxpresso/MIMXRT1015/MIMXRT1015_ram_flashloader.ld
    # )
    mcux_add_armgcc_linker_script(
        TARGETS release
        BASE_PATH ${SdkRootDirPath}
        LINKER middleware/mcu_bootloader/targets/common/linker/gcc/MIMXRT1015/MIMXRT1015_ram_flashloader.ld
    )
endif()

if(CONFIG_MCUX_PRJSEG_middleware.mcu-boot.MIMXRT1011_ram_flashloader_linker)
    mcux_add_iar_linker_script(
        TARGETS release
        BASE_PATH ${SdkRootDirPath}
        LINKER middleware/mcu_bootloader/targets/common/linker/iar/MIMXRT1011/MIMXRT1011_ram_flashloader.icf
    )
    mcux_add_mdk_linker_script(
        TARGETS release
        BASE_PATH ${SdkRootDirPath}
        LINKER middleware/mcu_bootloader/targets/common/linker/arm/MIMXRT1011/MIMXRT1011_ram_flashloader.scf
    )
    # mcux_add_mcux_linker_script(
        # TARGETS release
        # BASE_PATH ${SdkRootDirPath}
        # LINKER middleware/mcu_bootloader/targets/common/linker/mcuxpresso/MIMXRT1011/MIMXRT1011_ram_flashloader.ld
    # )
    mcux_add_armgcc_linker_script(
        TARGETS release
        BASE_PATH ${SdkRootDirPath}
        LINKER middleware/mcu_bootloader/targets/common/linker/gcc/MIMXRT1011/MIMXRT1011_ram_flashloader.ld
    )
endif()

if(CONFIG_MCUX_PRJSEG_middleware.mcu-boot.MIMXRT1024_ram_flashloader_linker)
    mcux_add_iar_linker_script(
        TARGETS release
        BASE_PATH ${SdkRootDirPath}
        LINKER middleware/mcu_bootloader/targets/common/linker/iar/MIMXRT1024/MIMXRT1024_ram_flashloader.icf
    )
    mcux_add_mdk_linker_script(
        TARGETS release
        BASE_PATH ${SdkRootDirPath}
        LINKER middleware/mcu_bootloader/targets/common/linker/arm/MIMXRT1024/MIMXRT1024_ram_flashloader.scf
    )
    # mcux_add_mcux_linker_script(
        # TARGETS release
        # BASE_PATH ${SdkRootDirPath}
        # LINKER middleware/mcu_bootloader/targets/common/linker/mcuxpresso/MIMXRT1024/MIMXRT1024_ram_flashloader.ld
    # )
    mcux_add_armgcc_linker_script(
        TARGETS release
        BASE_PATH ${SdkRootDirPath}
        LINKER middleware/mcu_bootloader/targets/common/linker/gcc/MIMXRT1024/MIMXRT1024_ram_flashloader.ld
    )
endif()

if(CONFIG_MCUX_PRJSEG_middleware.mcu-boot.MIMXRT1176_ram_flashloader_linker)
    mcux_add_iar_linker_script(
        TARGETS release
        BASE_PATH ${SdkRootDirPath}
        LINKER middleware/mcu_bootloader/targets/common/linker/iar/MIMXRT1176/MIMXRT1176_ram_flashloader.icf
    )
    mcux_add_mdk_linker_script(
        TARGETS release
        BASE_PATH ${SdkRootDirPath}
        LINKER middleware/mcu_bootloader/targets/common/linker/arm/MIMXRT1176/MIMXRT1176_ram_flashloader.scf
    )
    # mcux_add_mcux_linker_script(
        # TARGETS release
        # BASE_PATH ${SdkRootDirPath}
        # LINKER middleware/mcu_bootloader/targets/common/linker/mcuxpresso/MIMXRT1176/MIMXRT1176_ram_flashloader.ld
    # )
    mcux_add_armgcc_linker_script(
        TARGETS release
        BASE_PATH ${SdkRootDirPath}
        LINKER middleware/mcu_bootloader/targets/common/linker/gcc/MIMXRT1176/MIMXRT1176_ram_flashloader.ld
    )
endif()

if(CONFIG_MCUX_PRJSEG_middleware.mcu-boot.MIMXRT1166_ram_flashloader_linker)
    mcux_add_iar_linker_script(
        TARGETS release
        BASE_PATH ${SdkRootDirPath}
        LINKER middleware/mcu_bootloader/targets/common/linker/iar/MIMXRT1166/MIMXRT1166_ram_flashloader.icf
    )
    mcux_add_mdk_linker_script(
        TARGETS release
        BASE_PATH ${SdkRootDirPath}
        LINKER middleware/mcu_bootloader/targets/common/linker/arm/MIMXRT1166/MIMXRT1166_ram_flashloader.scf
    )
    # mcux_add_mcux_linker_script(
        # TARGETS release
        # BASE_PATH ${SdkRootDirPath}
        # LINKER middleware/mcu_bootloader/targets/common/linker/mcuxpresso/MIMXRT1166/MIMXRT1166_ram_flashloader.ld
    # )
    mcux_add_armgcc_linker_script(
        TARGETS release
        BASE_PATH ${SdkRootDirPath}
        LINKER middleware/mcu_bootloader/targets/common/linker/gcc/MIMXRT1166/MIMXRT1166_ram_flashloader.ld
    )
endif()

if(CONFIG_MCUX_PRJSEG_middleware.mcu-boot.MIMXRT1189_ram_flashloader_linker)
    mcux_add_iar_linker_script(
        TARGETS release
        BASE_PATH ${SdkRootDirPath}
        LINKER middleware/mcu_bootloader/targets/common/linker/iar/MIMXRT1189/MIMXRT1189_ram_flashloader.icf
    )
    mcux_add_mdk_linker_script(
        TARGETS release
        BASE_PATH ${SdkRootDirPath}
        LINKER middleware/mcu_bootloader/targets/common/linker/arm/MIMXRT1189/MIMXRT1189_ram_flashloader.scf
    )
    #mcux_add_mcux_linker_script(
    #    TARGETS release
    #    BASE_PATH ${SdkRootDirPath}
    #    LINKER middleware/mcu_bootloader/targets/common/linker/mcuxpresso/MIMXRT1189/MIMXRT1189_ram_flashloader.ld
    #)
    mcux_add_armgcc_linker_script(
        TARGETS release
        BASE_PATH ${SdkRootDirPath}
        LINKER middleware/mcu_bootloader/targets/common/linker/gcc/MIMXRT1189/MIMXRT1189_ram_flashloader.ld
    )
endif()

if(CONFIG_MCUX_PRJSEG_middleware.mcu-boot.MIMXRT1187_ram_flashloader_linker)
    mcux_add_iar_linker_script(
        TARGETS release
        BASE_PATH ${SdkRootDirPath}
        LINKER middleware/mcu_bootloader/targets/common/linker/iar/MIMXRT1187/MIMXRT1187_ram_flashloader.icf
    )
    mcux_add_mdk_linker_script(
        TARGETS release
        BASE_PATH ${SdkRootDirPath}
        LINKER middleware/mcu_bootloader/targets/common/linker/arm/MIMXRT1187/MIMXRT1187_ram_flashloader.scf
    )
    # mcux_add_mcux_linker_script(
        # TARGETS release
        # BASE_PATH ${SdkRootDirPath}
        # LINKER middleware/mcu_bootloader/targets/common/linker/mcuxpresso/MIMXRT1187/MIMXRT1187_ram_flashloader.ld
    # )
    mcux_add_armgcc_linker_script(
        TARGETS release
        BASE_PATH ${SdkRootDirPath}
        LINKER middleware/mcu_bootloader/targets/common/linker/gcc/MIMXRT1187/MIMXRT1187_ram_flashloader.ld
    )
endif()

if(CONFIG_MCUX_PRJSEG_middleware.mcu-boot.MIMXRT1186_ram_flashloader_linker)
    mcux_add_iar_linker_script(
        TARGETS release
        BASE_PATH ${SdkRootDirPath}
        LINKER middleware/mcu_bootloader/targets/common/linker/iar/MIMXRT1186/MIMXRT1186_ram_flashloader.icf
    )
    mcux_add_mdk_linker_script(
        TARGETS release
        BASE_PATH ${SdkRootDirPath}
        LINKER middleware/mcu_bootloader/targets/common/linker/arm/MIMXRT1186/MIMXRT1186_ram_flashloader.scf
    )
    #mcux_add_mcux_linker_script(
    #    TARGETS release
    #    BASE_PATH ${SdkRootDirPath}
    #    LINKER middleware/mcu_bootloader/targets/common/linker/mcuxpresso/MIMXRT1186/MIMXRT1186_ram_flashloader.ld
    #)
    mcux_add_armgcc_linker_script(
        TARGETS release
        BASE_PATH ${SdkRootDirPath}
        LINKER middleware/mcu_bootloader/targets/common/linker/gcc/MIMXRT1186/MIMXRT1186_ram_flashloader.ld
    )
endif()

if(CONFIG_MCUX_PRJSEG_middleware.mcu-boot.LPC54018_ram_flashloader_linker)
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/iar/LPC54018/LPC54018_ram_flashloader.icf
        TOOLCHAINS iar
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/arm/LPC54018/LPC54018_ram_flashloader.scf
        TOOLCHAINS mdk
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/mcuxpresso/LPC54018/LPC54018_ram_flashloader.ld
        TOOLCHAINS mcux
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
    mcux_add_source(
        SOURCES middleware/mcu_bootloader/targets/common/linker/gcc/LPC54018/LPC54018_ram_flashloader.ld
        TOOLCHAINS armgcc
        BASE_PATH ${SdkRootDirPath}/middleware/mcu_bootloader/component/
    )
endif()

if(CONFIG_MCUX_PRJSEG_middleware.mcu-boot.LPC54S018M_ram_flashloader_linker)
    mcux_add_iar_linker_script(
        TARGETS release
        BASE_PATH ${SdkRootDirPath}
        LINKER middleware/mcu_bootloader/targets/common/linker/iar/LPC54S018M/LPC54S018M_ram_flashloader.icf
    )
    mcux_add_mdk_linker_script(
        TARGETS release
        BASE_PATH ${SdkRootDirPath}
        LINKER middleware/mcu_bootloader/targets/common/linker/arm/LPC54S018M/LPC54S018M_ram_flashloader.scf
    )
    #mcux_add_mcux_linker_script(
    #    TARGETS release
    #    BASE_PATH ${SdkRootDirPath}
    #    LINKER middleware/mcu_bootloader/targets/common/linker/mcuxpresso/LPC54S018M/LPC54S018M_ram_flashloader.ld
    #)
    mcux_add_armgcc_linker_script(
        TARGETS release
        BASE_PATH ${SdkRootDirPath}
        LINKER middleware/mcu_bootloader/targets/common/linker/gcc/LPC54S018M/LPC54S018M_ram_flashloader.ld
    )
endif()

if(CONFIG_MCUX_PRJSEG_middleware.mcu-boot.LPC54S018_ram_flashloader_linker)
    mcux_add_iar_linker_script(
        TARGETS release
        BASE_PATH ${SdkRootDirPath}
        LINKER middleware/mcu_bootloader/targets/common/linker/iar/LPC54S018/LPC54S018_ram_flashloader.icf
    )
    mcux_add_mdk_linker_script(
        TARGETS release
        BASE_PATH ${SdkRootDirPath}
        LINKER middleware/mcu_bootloader/targets/common/linker/arm/LPC54S018/LPC54S018_ram_flashloader.scf
    )
    #mcux_add_mcux_linker_script(
    #    TARGETS release
    #    BASE_PATH ${SdkRootDirPath}
    #    LINKER middleware/mcu_bootloader/targets/common/linker/mcuxpresso/LPC54S018/LPC54S018_ram_flashloader.ld
    #)
    mcux_add_armgcc_linker_script(
        TARGETS release
        BASE_PATH ${SdkRootDirPath}
        LINKER middleware/mcu_bootloader/targets/common/linker/gcc/LPC54S018/LPC54S018_ram_flashloader.ld
    )
endif()

if(CONFIG_MCUX_PRJSEG_middleware.mcu-boot.MIMXRT1152_ram_flashloader_linker)
    mcux_add_iar_linker_script(
        TARGETS release
        BASE_PATH ${SdkRootDirPath}
        LINKER middleware/mcu_bootloader/targets/common/linker/iar/MIMXRT1152/MIMXRT1152_ram_flashloader.icf
    )
    mcux_add_mdk_linker_script(
        TARGETS release
        BASE_PATH ${SdkRootDirPath}
        LINKER middleware/mcu_bootloader/targets/common/linker/arm/MIMXRT1152/MIMXRT1152_ram_flashloader.scf
    )
    # mcux_add_mcux_linker_script(
        # TARGETS release
        # BASE_PATH ${SdkRootDirPath}
        # LINKER middleware/mcu_bootloader/targets/common/linker/mcuxpresso/MIMXRT1152/MIMXRT1152_ram_flashloader.ld
    # )
    mcux_add_armgcc_linker_script(
        TARGETS release
        BASE_PATH ${SdkRootDirPath}
        LINKER middleware/mcu_bootloader/targets/common/linker/gcc/MIMXRT1152/MIMXRT1152_ram_flashloader.ld
    )
endif()
