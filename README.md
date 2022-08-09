# Fork Info

This is a fork of libretro-dolphin-launcher to add even hackier Windows support for invoking Dolphin directly from the RetroArch
menu without using the forked Dolphin core. It also adds support for the modern [RVZ rom format](https://es.dolphin-emu.org/blog/2020/07/05/dolphin-progress-report-may-and-june-2020/#50-12188-support-for-rvz-and-wia-disc-formats-by-josjuice). **Please note that this project (like the original) runs Dolphin via a
`system` call, which is pretty unsafe and could lead to command injection from untrusted inputs. If you are only running
games from sources you trust, you should be okay (but please be cautious!).** To use, install the core as normal and then set the environment variable
`DOLPHIN_DIR` to the path where your `Dolphin.exe` is located (no quotes!). You should then be able to launch games via
the RetroArch UI.


# libretro-dolphin-launcher

Launch Nintendo Wii and GameCube games through [Dolphin](https://dolphin-emu.org) native, directly from [RetroArch](http://www.libretro.com/).

![Dolphin Launcher Screenshot](screenshot.jpg)

Note: This is a big hack, and it's recommended to use the [Dolphin Core](https://github.com/libretro/dolphin) instead.

## Installation

1. Compile the core
    ``` bash
    git clone https://github.com/RobLoach/libretro-dolphin-launcher.git
    cd libretro-dolphin-launcher
    make
    ```

2. Copy the core file to the RetroArch cores directory
    ``` bash
    cp dolphin_launcher_libretro.so /usr/lib/libretro/
    cp dolphin_launcher_libretro.info /usr/share/libretro/info/
    ```

3. Make sure [Dolphin](http://dolphin-emu.org) [is installed](https://dolphin-emu.org/download/?ref=btn). You should be able to run at least one of the following commands:
    ``` bash
    dolphin-emu --version
    dolphin-emu-nogui --version
    flatpak run org.DolphinEmu.dolphin-emu --version
    ```

## Usage

1. Scan Nintendo GameCube and Wii games in RetroArch

2. Launch the games directly from the RetroArch menu

3. Alternatively, you can run games through the command line
    ``` bash
    retroarch -L dolphin_launcher_libretro.so Mario.gcm
    ```

## Contributors

- [Rob Loach](http://github.com/robloach)
- [Alcaro](https://github.com/Alcaro)
