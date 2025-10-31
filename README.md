# QuackStation
This project started as an archived copy of DuckStation, a PSX emulator with a Qt front-end.

# Why fork Duck Station?
Prior to a license change that moved it from being a free and open source PSX emulator, DuckStation wss basically the only modern PSX emulator available for Linux and on Flathub. However, as of commit `25bc8a64803df7e702db66e0f11d7b7d0fdc99f2` on 1 September 2024, the main developer of DuckStation, stenzek, updated their license, changing it from the GPLv3 license to the PolyForm Strict License 1.0.0, which is a source available but proprietary (non-free) software license. It was later switched to the CC-BY-NC-ND license, which is also not a free and open source license, and is also not meant for licensing software under. This, plus stenzek making other erratic moves such as threatening to break Arch Linux users from maintaining an AUR package, made me worry about the future of PSX emulation on Linux. The final nail in the coffin was that in late October 2025, the FlatHub package was marked as deprecated and is no longer being updated. As it is not under a FOSS license anymore and stenzek has been behaving rather rudely and erractically to the FOSS and especially the Linux community, I thought somebody would step up to fork the final FOSS version of DuckStation. Unfortunately, until 30 October 2025, nobody stepped up to properly fork the final GPLv3 version of DuckStation, leaving FlatHub without _any_ PSX emulator at all.

For those who were wondering, the change that officially moved DuckStation from the GPLv3 to the first non FOSS license was shown here: <https://github.com/stenzek/duckstation/commit/9ca6b5430fb358b39f21ce0b2fc0268de954dd23>

The final GPLv3 version of DuckStation had been archived at https://codeberg.org/vimuser/duckstation by Leah Rowe. A massive thank you to her for doing this so I don't have to worry about "GPL violations" for accidently looking at post FOSS DuckStation.

Because of all of the above and also because the version of Qt (the front-end for DuckStation) that the final version of DuckStation used is now end of life, I have finally decided to fork the final version of DuckStation that was under the GPLv3 that Leah had archived and keep maintaining the code base and hopefully accept improvements to it to hopefully match or even exceed what DuckStation had been as FOSS and is currently doing as propietary software.

I am open and welcome to any contributions that can help me keep the FOSS PSX emulation dream alive!

# Why change the name?
Unfortunately, I cannot use the DuckStation name for this project, as that is very likely a trademark held by stenzek, and it is very unlikely that he will allow me or others to use it for this project. As such, I have changed the name of the project from DuckStation to QuackStation.

In addition, because the logo for DuckStation is also likely a trademark held by stenzek, I am urgently seeking a new logo, even a temporary one, to replace the current one also used by DuckStation. (Please note that any of these submitted logos must be released under a CC-BY-SA compatible license for me to accept it into the project.)

## So... Why the current name "QuackStation"?
Well, "quack" is the sound ducks make, and a "quack" is also used to denorte a person who pretends in some way to have skills, knowledge, or other qualifications they do not possess. That's why the name was chosen.

# License
QuackStation is licensed under the GNU GPLv3 or later, and all contributions to the code base going forward must be compatible with this license.
However, as the license that the final release of DuckStation that was released under was _only_ licensed under the GNU GPLv3 (without the "or later" clause), it is (at least for now) for all intents and purposes under the GNU GPLv3 only.
The terms of the license are contained in the LICENSE file.

## Disclaimers
- This project was forked from DuckStation, which was (c) September 2019 - September 2024 stenzek and other contributors.
  - "DuckStation" and its logo are trademarks of stenzek, likely held by stenzek. This project is no longer affiliated with DuckStation and is a hard fork of the final FOSS release.
- "PlayStation" and "PSX" are registered trademarks of Sony Interactive Entertainment Europe Limited. This project is not affiliated in any way with Sony Interactive Entertainment.

[Features](#features) | [Downloading and Running](#downloading-and-running) | [Building](#building) | [Disclaimers](#disclaimers)

**Latest Builds for Windows 10/11 (x64/ARM64), Linux (AppImage/Flatpak), and macOS (11.0+ Universal):** https://github.com/cameronbosch/quackstation/releases/tag/latest

**Game Compatibility List:** _This needs to be redone._

**Discord Server:** Currently does not exist.

QuackStation is an simulator/emulator of the Sony PlayStation(TM) console, focusing on playability, speed, and long-term maintainability. The goal is to be as accurate as possible while maintaining performance suitable for low-end devices. "Hack" options are discouraged, the default configuration should support all playable games with only some of the enhancements having compatibility issues.

A PS1 or PS2 "BIOS" ROM image is required to to start the emulator and to play games. You can use an image from any hardware version or region, although mismatching game regions and BIOS regions may have compatibility issues. A ROM image is not provided with the emulator for legal reasons, you should dump this from your own console using Caetla or other means.

## Features

QuackStation features a fully-featured frontend built using Qt, as well as a fullscreen/TV UI based on Dear ImGui.

<p align="center">
  <img src="https://raw.githubusercontent.com/cameronbosch/quackstation/md-images/main-qt.png" alt="Main Window Screenshot" />
  <img src="https://raw.githubusercontent.com/cameronbosch/quackstation/md-images/bigduck.png" alt="Fullscreen UI Screenshot" />
</p>

Other features include:

 - CPU Recompiler/JIT (x86-64, armv7/AArch32, AArch64, RISC-V/RV64).
 - Hardware (D3D11, D3D12, OpenGL, Vulkan, Metal) and software rendering.
 - Upscaling, texture filtering, and true colour (24-bit) in hardware renderers.
 - Accurate blending via Rasterizer Order Views/Fragment Shader Interlock.
 - PGXP for geometry precision, texture correction, and depth buffer emulation.
 - Motion adaptive deinterlacing.
 - Adaptive downsampling filter.
 - Screen rotation for vertical or "TATE" shmup games.
 - Post processing shader chains (GLSL and Reshade FX).
 - "Fast boot" for skipping BIOS splash/intro.
 - Save state support, with runahead and rewind.
 - Windows, Linux, macOS support.
 - Supports reading directly from CD, bin/cue images, raw bin/img files, MAME CHD, single-track ECM, MDS/MDF, and unencrypted PBP formats.
 - Preloading of disc images to RAM to avoid disk sleeping hitches.
 - Automatic loading/applying of PPF patches.
 - Direct booting of homebrew executables.
 - Direct loading of Portable Sound Format (psf) files.
 - Time stretched audio when running outside of 100% speed, and surround sound expansion.
 - Digital and analog controllers for input (rumble is forwarded to host).
 - GunCon and Justifier lightgun support (simulated with mouse).
 - NeGcon support.
 - Qt and "Big Picture" UI.
 - Automatic updates with preview and latest channels.
 - Automatic content scanning - game titles/hashes are provided by redump.org.
 - Optional automatic switching of memory cards for each game.
 - Supports loading cheats from existing lists.
 - Memory card editor and save importer.
 - Emulated CPU overclocking.
 - Integrated and remote debugging.
 - Multitap controllers (up to 8 devices).
 - RetroAchievements.
 - Discord Rich Presence.
 - Video capture with Media Foundation (Windows) and [FFmpeg](https://www.ffmpeg.org/) (All Platforms) backends.

## System Requirements
 - A CPU faster than a potato. But it needs to be x86_64 (SSE4.1), AArch32/armv7, AArch64/ARMv8, or RISC-V/RV64.
 - For the hardware renderers, a GPU capable of OpenGL 3.1/OpenGL ES 3.1/Direct3D 11 Feature Level 10.0 (or Vulkan 1.0) and above. So, basically anything made in the last 10 years or so.
 - SDL, XInput or DInput compatible game controller (e.g. XB360/XBOne/XBSeries). DualShock 3 users on Windows will need to install the official DualShock 3 drivers included as part of PlayStation Now.

## Downloading and running
Binaries of QuackStation for Windows x64/ARM64, Linux x86_64 (in AppImage/Flatpak formats), and macOS Universal Binaries are available via GitHub Releases and are automatically built with every commit/push. Binaries or packages distributed through other sources may be out of date and are not supported by the developer, please speak to them for support, not us.

For x86 machines (most systems), you will need a CPU that supports the SSE4.1 instruction set. This includes all CPUs manufactured after 2007. If you want to use QuackStation with a CPU that is older, [v0.1-6995](https://github.com/cameronbosch/quackstation/releases/tag/v0.1-6995) is the last version that does not require SSE4.1.

### Windows

QuackStation **requires** Windows 10/11, specifically version 1809 or newer. If you are still using Windows 7/8/8.1, QuackStation **will not run** on your operating system. Running these operating systems in 2023 should be considered a security risk, and I would recommend updating to something which receives vendor support.
If you must use an older operating system, [v0.1-5624](https://github.com/cameronbosch/quackstation/releases/tag/v0.1-5624) is the last version which will run. But do not expect to recieve any assistance, these builds are no longer supported.

To download:
 - Go to https://github.com/cameronbosch/quackstation/releases/tag/latest, and download the Windows x64 build. This is a zip archive containing the prebuilt binary.
 - Alternatively, direct download link: https://github.com/cameronbosch/quackstation/releases/download/latest/quackstation-windows-x64-release.zip
 - Extract the archive **to a subdirectory**. The archive has no root subdirectory, so extracting to the current directory will drop a bunch of files in your download directory if you do not extract to a subdirectory.

Once downloaded and extracted, you can launch the emulator with `quackstation-qt-x64-ReleaseLTCG.exe`. Follow the Setup Wizard to get started.

**If you get an error about `vcruntime140_1.dll` being missing, you will need to update your Visual C++ runtime.** You can do that from this page: https://support.microsoft.com/en-au/help/2977003/the-latest-supported-visual-c-downloads. Specifically, you want the x64 runtime, which can be downloaded from https://aka.ms/vs/17/release/vc_redist.x64.exe.

### Linux

The only supported versions of DuckStation for Linux are the AppImage and Flatpak in the releases page. If you installed DuckStation from another source or distribution (e.g. EmuDeck), you should contact the packager for support, we have no control over it.

We plan to offer an official release on [Flathub](https://flathub.org/) again once the project gets back on track. This release will synchronized with the latest rolling/stable release on GitHub. This will become the primary and recommended way to use QuackStation once we get back on track.

You **should not** install DuckStation from unofficial repositories such as the AUR, they are **known to be broken**.

#### AppImage

The AppImages require a distribution equivalent to Ubuntu 22.04 or newer to run.

 - Go to https://github.com/cameronbosch/quackstation/releases/tag/latest, and download `quackstation-x64.AppImage`.
 - Run `chmod a+x` on the downloaded AppImage -- following this step, the AppImage can be run like a typical executable.
 - You may need to install libfuse2 or libfuse2t64 [to get AppImages working on newer versions of Ubuntu](https://itsfoss.com/cant-run-appimage-ubuntu/).

#### Flatpak

 - Go to https://github.com/cameronbosch/quackstation/releases/tag/latest, and download `quackstation-x64.flatpak`.
 - Run `flatpak install ./quackstation-x64.flatpak`.

or, if you have FlatHub set up:
 - Run `flatpak install org.quackstation.QuackStation`. Please note that as of 30 October 2025, this will not work for now.

Use `flatpak run org.quackstation.QuackStation` to start, or select `QuackStation` in the launcher of your desktop environment. Follow the Setup Wizard to get started.
 
### macOS

Universal MacOS builds are provided for both x64 and ARM64 (Apple Silicon).

MacOS Big Sir (11.0) is required, as this is also the minimum requirement for Qt.

To download:
 - Go to https://github.com/cameronbosch/quackstation/releases/tag/latest, and download `quackstation-mac-release.zip`.
 - Extract the zip by double-clicking it.
 - Open QuackStation.app, optionally moving it to your desired location first.
 - Depending on GateKeeper configuration, you may need to right click -> Open the first time you run it, as code signing certificates are out of the question for a project which brings in zero revenue. This may be harder on macOS Sequoia and later due to changes from Apple in Gatekeeper making running unsigned apps basically unfeasible right now.
 
### Android

Currently unmaintained.

**No support is provided for the Android app**, it is free and your expectations should be in line with that. Please **do not** email me about issues about it, or ask for help, you will be ignored.

To use:
1. Install and run the app for the first time.
2. Follow the setup wizard.

If you have an external controller, you will need to map the buttons and sticks in settings.

### LibCrypt protection and SBI files

A number of PAL region games use LibCrypt protection, requiring additional CD subchannel information to run properly. libcrypt not functioning usually manifests as hanging or crashing, but can sometimes affect gameplay too, depending on how the game implemented it.

For these games, make sure that the CD image and its corresponding SBI (.sbi) file have the same name and are placed in the same directory. DuckStation will automatically load the SBI file when it is found next to the CD image.

For example, if your disc image was named `Spyro3.cue`, you would place the SBI file in the same directory, and name it `Spyro3.sbi`.

CHD images with built-in subchannel information are also supported.

## Building

### Windows
Requirements:
 - Visual Studio 2022


1. Clone the respository: `git clone https://github.com/cameronbosch/quackstation.git`.
2. Download the dependencies pack from https://github.com/cameronbosch/quackstation-ext-qt-minimal/releases/download/latest/deps-x64.7z, and extract it to `dep\msvc`.
3. Open the Visual Studio solution `duckstation.sln` in the root, or "Open Folder" for cmake build.
4. Build solution.
5. Binaries are located in `bin/x64`.
6. Run `quackstation-qt-x64-Release.exe` or whichever config you used.

### Linux

#### Required Dependencies

Ubuntu/Debian package names:
```
build-essential clang cmake curl extra-cmake-modules git libasound2-dev libcurl4-openssl-dev libdbus-1-dev libdecor-0-dev libegl-dev libevdev-dev libfontconfig-dev libfreetype-dev libgtk-3-dev libgudev-1.0-dev libharfbuzz-dev libinput-dev libopengl-dev libpipewire-0.3-dev libpulse-dev libssl-dev libudev-dev libwayland-dev libx11-dev libx11-xcb-dev libxcb1-dev libxcb-composite0-dev libxcb-cursor-dev libxcb-damage0-dev libxcb-glx0-dev libxcb-icccm4-dev libxcb-image0-dev libxcb-keysyms1-dev libxcb-present-dev libxcb-randr0-dev libxcb-render0-dev libxcb-render-util0-dev libxcb-shape0-dev libxcb-shm0-dev libxcb-sync-dev libxcb-util-dev libxcb-xfixes0-dev libxcb-xinput-dev libxcb-xkb-dev libxext-dev libxkbcommon-x11-dev libxrandr-dev lld llvm nasm ninja-build pkg-config zlib1g-dev
```

Fedora package names:
```
alsa-lib-devel brotli-devel clang cmake dbus-devel egl-wayland-devel extra-cmake-modules fontconfig-devel gcc-c++ gtk3-devel libavcodec-free-devel libavformat-free-devel libavutil-free-devel libcurl-devel libdecor-devel libevdev-devel libICE-devel libinput-devel libSM-devel libswresample-free-devel libswscale-free-devel libX11-devel libXau-devel libxcb-devel libXcomposite-devel libXcursor-devel libXext-devel libXfixes-devel libXft-devel libXi-devel libxkbcommon-devel libxkbcommon-x11-devel libXpresent-devel libXrandr-devel libXrender-devel lld llvm make mesa-libEGL-devel mesa-libGL-devel nasm ninja-build openssl-devel patch pcre2-devel perl-Digest-SHA pipewire-devel pulseaudio-libs-devel systemd-devel wayland-devel xcb-util-cursor-devel xcb-util-devel xcb-util-errors-devel xcb-util-image-devel xcb-util-keysyms-devel xcb-util-renderutil-devel xcb-util-wm-devel xcb-util-xrm-devel zlib-devel
```

#### Building

1. Clone the repository: `git clone https://github.com/cameronbosch/quackstation.git`, `cd quackstation`.
2. Build dependencies. You can save these outside of the tree if you like. This will take a while. `scripts/deps/build-dependencies-linux.sh deps`.
3. Run CMake to configure the build system. Assuming a build subdirectory of `build-release`, run `cmake -B build-release -DCMAKE_C_COMPILER=clang -DCMAKE_CXX_COMPILER=clang++ -DCMAKE_EXE_LINKER_FLAGS_INIT="-fuse-ld=lld" -DCMAKE_MODULE_LINKER_FLAGS_INIT="-fuse-ld=lld" -DCMAKE_SHARED_LINKER_FLAGS_INIT="-fuse-ld=lld" -DCMAKE_PREFIX_PATH="$PWD/deps" -G Ninja`. If you want a release (optimized) build, include `-DCMAKE_BUILD_TYPE=Release -DCMAKE_INTERPROCEDURAL_OPTIMIZATION=ON`.
4. Compile the source code. For the example above, run `ninja -C build-release`
5. Run the binary, located in the build directory under `./build-release/bin/quackstation-qt`.

### macOS

Requirements:
 - CMake
 - Xcode


1. Clone the repository: `git clone https://github.com/cameronbosch/quackstation.git`.
2. Build the dependencies. This will take a while. `scripts/deps/build-dependencies-mac.sh deps`.
2. Run CMake to configure the build system: `cmake -Bbuild-release -DCMAKE_BUILD_TYPE=Release -DCMAKE_INTERPROCEDURAL_OPTIMIZATION=ON -DCMAKE_PREFIX_PATH="$PWD/deps"`. 
4. Compile the source code: `cmake --build build-release --parallel`.
5. Run the binary, located in the build directory under `bin/QuackStation.app`.

## User Directories
The "User Directory" is where you should place your BIOS images, where settings are saved to, and memory cards/save states are saved by default.
An optional [SDL game controller database file](#sdl-game-controller-database) can be also placed here.

This is located in the following places depending on the platform you're using:

- Windows: My Documents\DuckStation
- Linux: `$XDG_DATA_HOME/duckstation`, or `~/.local/share/duckstation`.
- macOS: `~/Library/Application Support/DuckStation`.

So, if you were using Linux, you would place your BIOS images in `~/.local/share/duckstation/bios`. This directory will be created upon running QuackStation
for the first time.

If you wish to use a "portable" build, where the user directory is the same as where the executable is located, create an empty file named `portable.txt`
in the same directory as the QuackStation executable.

## Bindings for Qt frontend
Your keyboard or game controller can be used to simulate a variety of PlayStation controllers. Controller input is supported through DInput, XInput, and SDL backends and can be changed through `Settings -> General Settings`.

To bind your input device, go to `Settings -> Controllers`. Each of the buttons/axes for the simulated controller will be listed, alongside the corresponding key/button on your device that it is currently bound to. To rebind, click the box next to the button/axis name, and press the key or button on your input device that you wish to bind to. When binding rumble, simply press any button on the controller you wish to send rumble to.

## SDL Game Controller Database
QuackStation releases ship with a database of game controller mappings for the SDL controller backend, courtesy of https://github.com/mdqinc/SDL_GameControllerDB. The included `gamecontrollerdb.txt` file can be found in the `resources` subdirectory of the QuackStation program directory.

If you are experiencing issues binding your controller with the SDL controller backend, you may need to add a custom mapping to the database file. Make a copy of `gamecontrollerdb.txt` and place it in your [user directory](#user-directories) (or directly in the program directory, if running in portable mode) and then follow the instructions in the [SDL_GameControllerDB repository](https://github.com/mdqinc/SDL_GameControllerDB) for creating a new mapping. Add this mapping to the new copy of `gamecontrollerdb.txt` and your controller should then be recognized properly.

## Default bindings
Controller 1:
 - **Left Stick:** W/A/S/D
 - **Right Stick:** T/F/G/H
 - **D-Pad:** Up/Left/Down/Right
 - **Triangle/Square/Circle/Cross:** I/J/L/K
 - **L1/R1:** Q/E
 - **L2/R2:** 1/3
 - **L3/R3:** 2/4
 - **Start:** Enter
 - **Select:** Backspace

Hotkeys:
 - **Escape:** Open Pause Menu
 - **F11:** Toggle Fullscreen
 - **Tab:** Temporarily Disable Speed Limiter
 - **Space:** Pause/Resume Emulation

## Disclaimers

Icon by (icon needed)

"PlayStation" and "PSX" are registered trademarks of Sony Interactive Entertainment Europe Limited. This project is not affiliated in any way with Sony Interactive Entertainment.
