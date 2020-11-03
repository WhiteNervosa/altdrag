AltDrag application coded by [@stefanstundin](https://github.com/stefansundin/altdrag).  

To compile:
- Install MinGW-w64 from https://sourceforge.net/projects/mingw-w64/files/Toolchains%20targetting%20Win32/Personal%20Builds/mingw-builds/installer/mingw-w64-install.exe/download:
- Install the i686 version, make sure to specify MinGW64-i686 as the installation folder
- Run these two scripts in separate elevated powershell windows both cd'd to the repo dir:

1. Watch and compile:
`nodemon -w altdrag.c -w .\hooks.c -w .\hookwindows_x64.c -w config/config.c -w include/autostart.c -w include/error.c -w include/languages.c -w include/localization.c -w include/tray.c -w include/update.c -w tools/export_l10n_ini.c -w tools/import_languages.c -w tools/ini.c -w tools/unhook.c -x .\build.bat`

2. Restart AltDrag.exe for testing: (3s delay to prevent conflict with compile processes)
nodemon --delay 3 -w .\AltDrag.exe -w .\AltDrag.ini -x start .\AltDrag.exe

This repository contains updated build options to enable some of the `gcc/ld` hardening options.

```powershell
> Get-PESecurity -Dir .

FileName         : X:\altdrag\bin\AltDrag.exe
ARCH             : I386
DotNET           : False
ASLR             : True
DEP              : True
Authenticode     : False
StrongNaming     : N/A
SafeSEH          : False
ControlFlowGuard : False
HighentropyVA    : False

FileName         : X:\altdrag\bin\hooks.dll
ARCH             : I386
DotNET           : False
ASLR             : True
DEP              : True
Authenticode     : False
StrongNaming     : N/A
SafeSEH          : False
ControlFlowGuard : False
HighentropyVA    : False

FileName         : X:\altdrag\bin\hooks_x64.dll
ARCH             : AMD64
DotNET           : False
ASLR             : True
DEP              : True
Authenticode     : False
StrongNaming     : N/A
SafeSEH          : N/A
ControlFlowGuard : False
HighentropyVA    : True

FileName         : X:\altdrag\bin\HookWindows_x64.exe
ARCH             : AMD64
DotNET           : False
ASLR             : True
DEP              : True
Authenticode     : False
StrongNaming     : N/A
SafeSEH          : N/A
ControlFlowGuard : False
HighentropyVA    : True
```
