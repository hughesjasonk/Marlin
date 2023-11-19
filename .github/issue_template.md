__Issues that do not follow this issue template will be closed__

<!--
- *Be sure you have fully read the release notes and flashing instructions before posting an issue here*
- *Check if there is an existing _open_ issue that describes your problem and add your comments there*
- *Check if your issue has been resolved on the latest source code - or if there is a closed issue pointing to the next release*
- *Check that you have flashed the correct firmware for your device*
- Check this milestone for what issues are already found and resolved, and for possible workarounds: https://github.com/CR6Community/Marlin/milestone/3?closed=1
-->

### Description

Source Code will not compile into firmware within VSCODE

### Steps to Reproduce

*If this is a Bug Report, please describe the steps needed to reproduce the issue*

1. Copy configuration files from Marlin-2.0.8.1-cr6-community-release-6.1\config\cr6-se-v4.5.2-mb to Marlin-2.0.8.1-cr6-community-release-6.1\Marlin
2. open Marlin-2.0.8.1-cr6-community-release-6.1 folder in VSCODE
3. Edit platformio.ini to default_envs = STM32F103RET6_creality
4. click build

**Expected behavior:** 

Firmware to compile

**Actual behavior:** 

Failed to compile

**Logging:**

Warning! Ignore unknown configuration option `monitor_flags` in section [env]
Warning! `src_filter` configuration option in section [env:DUE] is deprecated and will be removed in the next release! Please use `build_src_filter` instead
Warning! `src_filter` configuration option in section [env:SAMD51_grandcentral_m4] is deprecated and will be removed in the next release! Please use `build_src_filter` instead
Warning! `src_filter` configuration option in section [env:malyan_M300] is deprecated and will be removed in the next release! Please use `build_src_filter` instead
Warning! `src_filter` configuration option in section [env:esp32] is deprecated and will be removed in the next release! Please use `build_src_filter` instead
Warning! `src_filter` configuration option in section [env:teensy31] is deprecated and will be removed in the next release! Please use `build_src_filter` instead
Warning! `src_filter` configuration option in section [env:teensy35] is deprecated and will be removed in the next release! Please use `build_src_filter` instead
Warning! `src_filter` configuration option in section [env:teensy36] is deprecated and will be removed in the next release! Please use `build_src_filter` instead
Warning! `src_filter` configuration option in section [env:teensy41] is deprecated and will be removed in the next release! Please use `build_src_filter` instead
Warning! `src_build_flags` configuration option in section [env:linux_native] is deprecated and will be removed in the next release! Please use `build_src_flags` instead
Warning! `src_filter` configuration option in section [env:linux_native] is deprecated and will be removed in the next release! Please use `build_src_filter` instead
Warning! `src_filter` configuration option in section [env:include_tree] is deprecated and will be removed in the next release! Please use `build_src_filter` instead
Processing STM32F103RET6_creality (platform: ststm32@~12.1; board: genericSTM32F103RE; framework: arduino)
---------------------------------------------------------------------------------------------------------------------------------------------------------------
Verbose mode can be enabled via `-v, --verbose` option
Libmaple modified and ready for post mortem debugging
CONFIGURATION: https://docs.platformio.org/page/boards/ststm32/genericSTM32F103RE.html
PLATFORM: ST STM32 (12.1.1) > STM32F103RE (64k RAM. 512k Flash)
HARDWARE: STM32F103RET6 72MHz, 64KB RAM, 512KB Flash
DEBUG: Current (jlink) External (blackmagic, cmsis-dap, jlink, stlink)
PACKAGES:
 - framework-arduinoststm32-maple @ 3.10000.201129 (1.0.0)
 - tool-stm32duino @ 1.0.2
 - toolchain-gccarmnoneeabi @ 1.70201.0 (7.2.1)
Converting Marlin.ino
LDF: Library Dependency Finder -> https://bit.ly/configure-pio-ldf
LDF Modes: Finder ~ chain, Compatibility ~ soft
Found 27 compatible libraries
Scanning dependencies...
Dependency Graph
|-- SoftwareSerialM @ 1.0.0
|-- STM32ADC @ 1.0
|-- EEPROM
|-- USBComposite for STM32F1 @ 0.99
|-- Wire @ 1.0
|-- Servo(STM32F1) @ 1.1.2
Building in release mode
RuntimeError: deque mutated during iteration:
  File "C:\Users\hughe\.platformio\penv\Lib\site-packages\platformio\builder\main.py", line 180:
    env.SConscript(env.GetExtraScripts("post"), exports="env")
  File "C:\Users\hughe\.platformio\packages\tool-scons\scons-local-4.5.2\SCons\Script\SConscript.py", line 598:
    return _SConscript(self.fs, *files, **subst_kw)
  File "C:\Users\hughe\.platformio\packages\tool-scons\scons-local-4.5.2\SCons\Script\SConscript.py", line 285:
    exec(compile(scriptdata, scriptname, 'exec'), call_stack[-1].globals)
  File "C:\Users\hughe\Desktop\Marlin-2.0.8.1-cr6-community-release-6.1\Marlin-2.0.8.1-cr6-community-release-6.1\buildroot\share\PlatformIO\scripts\custom_board.py", line 9:
    marlin.relocate_firmware(address)
  File "C:\Users\hughe\Desktop\Marlin-2.0.8.1-cr6-community-release-6.1\Marlin-2.0.8.1-cr6-community-release-6.1\buildroot\share\PlatformIO\scripts\marlin.py", line 27:
    replace_define("VECT_TAB_ADDR", address)
  File "C:\Users\hughe\Desktop\Marlin-2.0.8.1-cr6-community-release-6.1\Marlin-2.0.8.1-cr6-community-release-6.1\buildroot\share\PlatformIO\scripts\marlin.py", line 20:
    for define in env['CPPDEFINES']:
================================================================= [FAILED] Took 9.61 seconds =================================================================

Environment             Status    Duration
----------------------  --------  ------------
STM32F103RET6_creality  FAILED    00:00:09.608
============================================================ 1 failed, 0 succeeded in 00:00:09.608 ============================================================

 *  The terminal process "C:\Users\hughe\.platformio\penv\Scripts\platformio.exe 'run'" terminated with exit code: 1. 
 *  Terminal will be reused by tasks, press any key to close it. 

### Additional Information

CR6-SE, Creality V4.5.2 mainboard

https://github.com/CR6Community/Marlin/archive/refs/tags/v2.0.7.3-cr6-community-release-6.zip
