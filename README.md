# MyTelegram – Rebranded Telegram Desktop Fork

This is a rebranded fork of [Telegram Desktop][telegram_desktop], designed to run side-by-side with the official Telegram Desktop on Windows 11. It is based on the complete source code of the official [Telegram][telegram] messenger desktop client, using the [Telegram API][telegram_api] and the [MTProto][telegram_proto] secure protocol.

## Key Differences from Official Telegram Desktop

**MyTelegram** can be installed and used simultaneously with official Telegram Desktop because:

- **Unique Application Identity**: Uses different AppUserModelID and GUIDs
- **Separate Data Directory**: Stores data in `%APPDATA%\MyTelegram` instead of `%APPDATA%\Telegram Desktop`
- **No Single-Instance Conflict**: Uses unique local server name for IPC
- **Manual Updates Only**: Auto-update functionality is disabled
- **Custom Branding**: Uses "MyTelegram" name and icon throughout the application
- **Independent Installation**: Installs to `C:\Program Files\MyTelegram` by default

This allows you to log into different Telegram accounts on the same machine simultaneously.

[![Version](https://badge.fury.io/gh/telegramdesktop%2Ftdesktop.svg)](https://github.com/telegramdesktop/tdesktop/releases)
[![Build Status](https://github.com/telegramdesktop/tdesktop/workflows/Windows./badge.svg)](https://github.com/telegramdesktop/tdesktop/actions)
[![Build Status](https://github.com/telegramdesktop/tdesktop/workflows/MacOS./badge.svg)](https://github.com/telegramdesktop/tdesktop/actions)
[![Build Status](https://github.com/telegramdesktop/tdesktop/workflows/Linux./badge.svg)](https://github.com/telegramdesktop/tdesktop/actions)

[![Preview of Telegram Desktop][preview_image]][preview_image_url]

The source code is published under GPLv3 with OpenSSL exception, the license is available [here][license].

## Supported systems

The latest version is available for

* [Windows 7 and above (64 bit)](https://telegram.org/dl/desktop/win64) ([portable](https://telegram.org/dl/desktop/win64_portable))
* [Windows 7 and above (32 bit)](https://telegram.org/dl/desktop/win) ([portable](https://telegram.org/dl/desktop/win_portable))
* [macOS 10.13 and above](https://telegram.org/dl/desktop/mac)
* [Linux static build for 64 bit](https://telegram.org/dl/desktop/linux)
* [Snap](https://snapcraft.io/telegram-desktop)
* [Flatpak](https://flathub.org/apps/details/org.telegram.desktop)

## Old system versions

Version **4.9.9** was the last that supports older systems

* [macOS 10.12](https://updates.tdesktop.com/tmac/tsetup.4.9.9.dmg)
* [Linux with glibc < 2.28 static build](https://updates.tdesktop.com/tlinux/tsetup.4.9.9.tar.xz)

Version **2.4.4** was the last that supports older systems

* [OS X 10.10 and 10.11](https://updates.tdesktop.com/tosx/tsetup-osx.2.4.4.dmg)
* [Linux static build for 32 bit](https://updates.tdesktop.com/tlinux32/tsetup32.2.4.4.tar.xz)

Version **1.8.15** was the last that supports older systems

* [Windows XP and Vista](https://updates.tdesktop.com/tsetup/tsetup.1.8.15.exe) ([portable](https://updates.tdesktop.com/tsetup/tportable.1.8.15.zip))
* [OS X 10.8 and 10.9](https://updates.tdesktop.com/tmac/tsetup.1.8.15.dmg)
* [OS X 10.6 and 10.7](https://updates.tdesktop.com/tmac32/tsetup32.1.8.15.dmg)

## Third-party

* Qt 6 ([LGPL](http://doc.qt.io/qt-6/lgpl.html)) and Qt 5.15 ([LGPL](http://doc.qt.io/qt-5/lgpl.html)) slightly patched
* OpenSSL 3.2.1 ([Apache License 2.0](https://www.openssl.org/source/apache-license-2.0.txt))
* WebRTC ([New BSD License](https://github.com/desktop-app/tg_owt/blob/master/LICENSE))
* zlib ([zlib License](http://www.zlib.net/zlib_license.html))
* LZMA SDK 9.20 ([public domain](http://www.7-zip.org/sdk.html))
* liblzma ([public domain](http://tukaani.org/xz/))
* Google Breakpad ([License](https://chromium.googlesource.com/breakpad/breakpad/+/master/LICENSE))
* Google Crashpad ([Apache License 2.0](https://chromium.googlesource.com/crashpad/crashpad/+/master/LICENSE))
* GYP ([BSD License](https://github.com/bnoordhuis/gyp/blob/master/LICENSE))
* Ninja ([Apache License 2.0](https://github.com/ninja-build/ninja/blob/master/COPYING))
* OpenAL Soft ([LGPL](https://github.com/kcat/openal-soft/blob/master/COPYING))
* Opus codec ([BSD License](http://www.opus-codec.org/license/))
* FFmpeg ([LGPL](https://www.ffmpeg.org/legal.html))
* Guideline Support Library ([MIT License](https://github.com/Microsoft/GSL/blob/master/LICENSE))
* Range-v3 ([Boost License](https://github.com/ericniebler/range-v3/blob/master/LICENSE.txt))
* Open Sans font ([Apache License 2.0](http://www.apache.org/licenses/LICENSE-2.0.html))
* Vazirmatn font ([SIL Open Font License 1.1](https://github.com/rastikerdar/vazirmatn/blob/master/OFL.txt))
* Emoji alpha codes ([MIT License](https://github.com/emojione/emojione/blob/master/extras/alpha-codes/LICENSE.md))
* xxHash ([BSD License](https://github.com/Cyan4973/xxHash/blob/dev/LICENSE))
* QR Code generator ([MIT License](https://github.com/nayuki/QR-Code-generator#license))
* CMake ([New BSD License](https://github.com/Kitware/CMake/blob/master/Copyright.txt))
* Hunspell ([LGPL](https://github.com/hunspell/hunspell/blob/master/COPYING.LESSER))
* Ada ([Apache License 2.0](https://github.com/ada-url/ada/blob/main/LICENSE-APACHE))

## Download Compiled Binary/Installer

**For Windows users** (Windows 7 and above): Pre-built installers and portable executables are automatically generated for every commit and available in the [GitHub Actions artifacts](https://github.com/goodthebest/tdesktopx/actions/workflows/win.yml).

To download:
1. Go to the [Windows workflow runs](https://github.com/goodthebest/tdesktopx/actions/workflows/win.yml)
2. Click on the latest successful run (green checkmark)
3. Scroll down to the "Artifacts" section
4. Download the appropriate artifact:
   - **Telegram_x64**: Windows 64-bit installer and executables
   - **Telegram_Win32**: Windows 32-bit installer and executables

The artifacts include:
- **MyTelegram-Setup-[version].exe**: Full installer for Windows (requires Windows 7 or later)
- **Telegram.exe**: Portable executable (can run without installation)
- **Updater.exe**: Update utility

## Build instructions

**Note**: MyTelegram is primarily focused on Windows. While the source supports other platforms, the rebranding customizations are Windows-specific.

* Windows [(32-bit)][win32] [(64-bit)][win64]
* [macOS][mac] (builds as standard Telegram Desktop)
* [GNU/Linux using Docker][linux] (builds as standard Telegram Desktop)

### Quick Start (Windows)

1. Install Visual Studio 2022 with Windows 10/11 SDK
2. Obtain Telegram API credentials (api_id and api_hash) from https://core.telegram.org/api/obtaining_api_id
3. Clone this repository: `git clone --recursive https://github.com/goodthebest/tdesktopx.git`
4. Run the build preparation script
5. Configure and build with your API credentials

See [docs/building-win.md](docs/building-win.md) for detailed instructions.

[//]: # (LINKS)
[telegram]: https://telegram.org
[telegram_desktop]: https://desktop.telegram.org
[telegram_api]: https://core.telegram.org
[telegram_proto]: https://core.telegram.org/mtproto
[license]: LICENSE
[win32]: docs/building-win.md
[win64]: docs/building-win-x64.md
[mac]: docs/building-mac.md
[linux]: docs/building-linux.md
[preview_image]: https://github.com/telegramdesktop/tdesktop/blob/dev/docs/assets/preview.png "Preview of Telegram Desktop"
[preview_image_url]: https://raw.githubusercontent.com/telegramdesktop/tdesktop/dev/docs/assets/preview.png
