---
title: "CLI "
tags: ""
---

## CMD
Symbolic Link

https://docs.microsoft.com/en-us/windows-server/administration/windows-commands/mklink

```bash

# Files
mklink Link Target

# /D para directorios
mklink /D "path_link" "path_target"
```

## Powershell
Symbolic Link

https://docs.microsoft.com/es-es/powershell/module/microsoft.powershell.management/new-item?view=powershell-7.1

Necesita saber 1) la ruta de acceso al objetivo del enlace 2) la ruta de acceso a la ubicación donde quiere el enlace 3) el nombre que quiere usar para referirse al enlace.

```bash
C:\> new-item -itemtype symboliclink -path <path to location> -name <the name> -value <path to target>
New-Item -ItemType SymbolicLink -Name Link -Target Target

```
