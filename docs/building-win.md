# Build instructions for Windows (MyTelegram)

This is a rebranded fork of Telegram Desktop called **MyTelegram**. It can run side-by-side with official Telegram Desktop on Windows 11.

- [Prepare folder](#prepare-folder)
- [Install third party software](#install-third-party-software)
- [Clone source code and prepare libraries](#clone-source-code-and-prepare-libraries)
- [Build the project](#build-the-project)
- [Building portable version](#building-portable-version)
- [Building installer](#building-installer)
- [Qt Visual Studio Tools](#qt-visual-studio-tools)

## Prepare folder

The build is done in **Visual Studio 2022** with **10.0.26100.0** SDK version.

Choose an empty folder for the future build, for example **D:\\TBuild**. It will be named ***BuildPath*** in the rest of this document. Create two folders there, ***BuildPath*\\ThirdParty** and ***BuildPath*\\Libraries**.

All commands (if not stated otherwise) will be launched from **x86 Native Tools Command Prompt for VS 2022.bat** (should be in **Start Menu > Visual Studio 2022** menu folder). Pay attention not to use any other Command Prompt.

### API Credentials

**MyTelegram uses test API credentials by default**, so you can build without obtaining your own credentials. For more information or to use custom credentials, see [api_credentials.md][api_credentials].

## Install third party software

* Download **Python 3.10** installer from [https://www.python.org/downloads/](https://www.python.org/downloads/) and install it with adding to PATH.
* Download **Git** installer from [https://git-scm.com/download/win](https://git-scm.com/download/win) and install it.

## Clone source code and prepare libraries

Open **x86 Native Tools Command Prompt for VS 2022.bat**, go to ***BuildPath*** and run

    git clone --recursive https://github.com/goodthebest/tdesktopx.git
    tdesktopx\Telegram\build\prepare\win.bat

## Build the project

Go to ***BuildPath*\\tdesktopx\\Telegram** and run:

    configure.bat

**Note:** Test API credentials are used automatically. If you need to use your own credentials, add: `-D TDESKTOP_API_ID=YOUR_API_ID -D TDESKTOP_API_HASH=YOUR_API_HASH`

**MyTelegram branding** is enabled by default via the `MYTELEGRAM_BRAND` CMake option. This automatically:
- Uses test API credentials (can be overridden)
- Disables auto-updates
- Uses separate data directory (%APPDATA%\MyTelegram)
- Uses unique single-instance identifier
- Enables side-by-side installation with official Telegram Desktop

* Open ***BuildPath*\\tdesktopx\\out\\Telegram.sln** in Visual Studio 2022
* Select Telegram project and press Build > Build Telegram (Debug and Release configurations)
* The result Telegram.exe will be located in **D:\TBuild\tdesktopx\out\Debug** (and **Release**)

## Building portable version

The Release build creates a portable version by default. Simply copy the contents of the **Release** folder to any location and run **Telegram.exe**. The application will store its data in the same folder.

## Building installer

To build the Windows installer using Inno Setup:

1. Download and install [Inno Setup](https://jrsoftware.org/isdl.php) (version 6.x or later)
2. Build the Release configuration as described above
3. Open **Telegram\build\setup.iss** in Inno Setup Compiler
4. Make sure the script variables point to your build output directory
5. Click **Build > Compile** to create the installer
6. The installer will be generated in the output directory specified in setup.iss

The installer will:
- Install to **C:\Program Files\MyTelegram** by default
- Create Start Menu shortcuts for MyTelegram
- Allow installation alongside official Telegram Desktop
- Use separate AppData directory for MyTelegram

### Qt Visual Studio Tools

For better debugging you may want to install Qt Visual Studio Tools:

* Open **Extensions** -> **Manage Extensions**
* Go to **Online** tab
* Search for **Qt**
* Install **Qt Visual Studio Tools** extension

[api_credentials]: api_credentials.md
