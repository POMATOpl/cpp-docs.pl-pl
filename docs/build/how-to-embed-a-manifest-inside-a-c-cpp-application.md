---
description: 'Dowiedz się więcej na temat: Jak osadzić Manifest w aplikacji C/C++'
title: 'Porady: osadzanie manifestu w aplikacji C/C++'
ms.date: 05/06/2019
helpviewer_keywords:
- manifests [C++]
- embedding manifests
- makefiles, updating to embed manifest
ms.assetid: ec0bac69-2fdc-466c-ab0d-710a22974e5d
ms.openlocfilehash: ce3bdd56b994498b223857b80989247fe9919e4c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97156349"
---
# <a name="how-to-embed-a-manifest-inside-a-cc-application"></a>Porady: osadzanie manifestu w aplikacji C/C++

Zalecamy osadzenie manifestu aplikacji lub biblioteki w końcowym pliku binarnym, ponieważ gwarantuje to poprawne zachowanie środowiska uruchomieniowego w większości scenariuszy. Domyślnie program Visual Studio próbuje osadzić Manifest podczas kompilowania projektu. Aby uzyskać więcej informacji, zobacz [generowanie manifestu w programie Visual Studio](manifest-generation-in-visual-studio.md). Jednak w przypadku kompilowania aplikacji przy użyciu programu NMAKE należy wprowadzić pewne zmiany w pliku reguł programu make. W tej sekcji przedstawiono sposób zmiany plików reguł programu make w taki sposób, aby automatycznie osadzał manifest w końcowym pliku binarnym.

## <a name="two-approaches"></a>Dwa podejścia

Istnieją dwa sposoby osadzenia manifestu wewnątrz aplikacji lub biblioteki.

- Jeśli nie wykonujesz kompilacji przyrostowej, możesz bezpośrednio osadzić Manifest przy użyciu wiersza polecenia podobnego do następującego w kroku po kompilacji:

   ```cmd
   mt.exe -manifest MyApp.exe.manifest -outputresource:MyApp.exe;1
   ```

   lub

   ```cmd
   mt.exe -manifest MyLibrary.dll.manifest -outputresource:MyLibrary.dll;2
   ```

   Użyj 1 dla EXE i 2 dla biblioteki DLL.

- Jeśli wykonujesz kompilację przyrostową, wykonaj następujące czynności:

  - Połącz plik binarny w celu wygenerowania pliku MyApp.exe. manifest.

  - Przekonwertuj manifest na plik zasobów.

  - Połącz ponownie (przyrostowo), aby osadzić zasób manifestu w pliku binarnym.

W poniższych przykładach pokazano, jak zmienić pliki reguł programu make w celu uwzględnienia obu tych technik.

## <a name="makefiles-before"></a>Pliki reguł programu make (przed)

Rozważmy skrypt NMAKE dla MyApp.exe, prostą aplikację utworzoną z jednego pliku:

```
# build MyApp.exe
!if "$(DEBUG)" == "1"
CPPFLAGS=$(CPPFLAGS) /MDd
LFLAGS=$(LFLAGS) /INCREMENTAL
!else
CPPFLAGS=$(CPPFLAGS) /MD
!endif

MyApp.exe : MyApp.obj
    link $** /out:$@ $(LFLAGS)

MyApp.obj : MyApp.cpp

clean :
    del MyApp.obj MyApp.exe
```

Jeśli ten skrypt jest uruchamiany bez zmian w programie Visual Studio, pomyślnie tworzy MyApp.exe. Tworzy również zewnętrzny plik manifestu MyApp.exe. manifest, do użytku przez system operacyjny w celu załadowania zestawów zależnych w czasie wykonywania.

Skrypt NMAKE dla MyLibrary.dll wygląda bardzo podobnie:

```
# build MyLibrary.dll
!if "$(DEBUG)" == "1"
CPPFLAGS=$(CPPFLAGS) /MDd
LFLAGS=$(LFLAGS) /DLL /INCREMENTAL

!else
CPPFLAGS=$(CPPFLAGS) /MD
LFLAGS=$(LFLAGS) /DLL

!endif

MyLibrary.dll : MyLibrary.obj
    link $** /out:$@ $(LFLAGS)

MyLibrary.obj : MyLibrary.cpp

clean :
    del MyLibrary.obj MyLibrary.dll
```

## <a name="makefiles-after"></a>Pliki reguł programu make (po)

Aby kompilować przy użyciu osadzonych manifestów, należy wprowadzić cztery małe zmiany w oryginalnych plikach reguł programu make. MyApp.exe pliku reguł programu make:

```
# build MyApp.exe
!include makefile.inc
#^^^^^^^^^^^^^^^^^^^^ Change #1. (Add full path if necessary.)

!if "$(DEBUG)" == "1"
CPPFLAGS=$(CPPFLAGS) /MDd
LFLAGS=$(LFLAGS) /INCREMENTAL
!else
CPPFLAGS=$(CPPFLAGS) /MD
!endif

MyApp.exe : MyApp.obj
    link $** /out:$@ $(LFLAGS)
    $(_VC_MANIFEST_EMBED_EXE)
#^^^^^^^^^^^^^^^^^^^^^^^^^^^^ Change #2

MyApp.obj : MyApp.cpp

clean :
    del MyApp.obj MyApp.exe
    $(_VC_MANIFEST_CLEAN)
#^^^^^^^^^^^^^^^^^^^^^^^^ Change #3

!include makefile.targ.inc
#^^^^^^^^^^^^^^^^^^^^^^^^^ Change #4. (Add full path if necessary.)
```

MyLibrary.dll pliku reguł programu make:

```
# build MyLibrary.dll
!include makefile.inc
#^^^^^^^^^^^^^^^^^^^^ Change #1. (Add full path if necessary.)

!if "$(DEBUG)" == "1"
CPPFLAGS=$(CPPFLAGS) /MDd
LFLAGS=$(LFLAGS) /DLL /INCREMENTAL

!else
CPPFLAGS=$(CPPFLAGS) /MD
LFLAGS=$(LFLAGS) /DLL

!endif

MyLibrary.dll : MyLibrary.obj
    link $** /out:$@ $(LFLAGS)
    $(_VC_MANIFEST_EMBED_DLL)
#^^^^^^^^^^^^^^^^^^^^^^^^^^^^ Change #2.

MyLibrary.obj : MyLibrary.cpp

clean :
    del MyLibrary.obj MyLibrary.dll
    $(_VC_MANIFEST_CLEAN)
#^^^^^^^^^^^^^^^^^^^^^^^^ Change #3.

!include makefile.targ.inc
#^^^^^^^^^^^^^^^^^^^^^^^^^ Change #4. (Add full path if necessary.)
```

Plik reguł programu make zawiera teraz dwa pliki, które wykonują rzeczywiste zadania, pliku reguł programu make. Inc.

Utwórz plik reguł programu make. Inc i skopiuj do niego następujące elementy:

```
# makefile.inc -- Include this file into existing makefile at the very top.

# _VC_MANIFEST_INC specifies whether build is incremental (1 - incremental).
# _VC_MANIFEST_BASENAME specifies name of a temporary resource file.

!if "$(DEBUG)" == "1"
CPPFLAGS=$(CPPFLAGS) /MDd
LFLAGS=$(LFLAGS) /INCREMENTAL
_VC_MANIFEST_INC=1
_VC_MANIFEST_BASENAME=__VC90.Debug

!else
CPPFLAGS=$(CPPFLAGS) /MD
_VC_MANIFEST_INC=0
_VC_MANIFEST_BASENAME=__VC90

!endif

####################################################
# Specifying name of temporary resource file used only in incremental builds:

!if "$(_VC_MANIFEST_INC)" == "1"
_VC_MANIFEST_AUTO_RES=$(_VC_MANIFEST_BASENAME).auto.res
!else
_VC_MANIFEST_AUTO_RES=
!endif

####################################################
# _VC_MANIFEST_EMBED_EXE - command to embed manifest in EXE:

!if "$(_VC_MANIFEST_INC)" == "1"

#MT_SPECIAL_RETURN=1090650113
#MT_SPECIAL_SWITCH=-notify_resource_update
MT_SPECIAL_RETURN=0
MT_SPECIAL_SWITCH=
_VC_MANIFEST_EMBED_EXE= \
if exist $@.manifest mt.exe -manifest $@.manifest -out:$(_VC_MANIFEST_BASENAME).auto.manifest $(MT_SPECIAL_SWITCH) & \
if "%ERRORLEVEL%" == "$(MT_SPECIAL_RETURN)" \
rc /r $(_VC_MANIFEST_BASENAME).auto.rc & \
link $** /out:$@ $(LFLAGS)

!else

_VC_MANIFEST_EMBED_EXE= \
if exist $@.manifest mt.exe -manifest $@.manifest -outputresource:$@;1

!endif

####################################################
# _VC_MANIFEST_CLEAN - command to clean resources files generated temporarily:

!if "$(_VC_MANIFEST_INC)" == "1"

_VC_MANIFEST_CLEAN=-del $(_VC_MANIFEST_BASENAME).auto.res \
    $(_VC_MANIFEST_BASENAME).auto.rc \
    $(_VC_MANIFEST_BASENAME).auto.manifest

!else

_VC_MANIFEST_CLEAN=

!endif

# End of makefile.inc
####################################################
```

Teraz Utwórz plik **reguł programu make. elowe. Inc** i skopiuj do niego następujące elementy:

```
# makefile.targ.inc - include this at the very bottom of the existing makefile

####################################################
# Commands to generate initial empty manifest file and the RC file
# that references it, and for generating the .res file:

$(_VC_MANIFEST_BASENAME).auto.res : $(_VC_MANIFEST_BASENAME).auto.rc

$(_VC_MANIFEST_BASENAME).auto.rc : $(_VC_MANIFEST_BASENAME).auto.manifest
    type <<$@
#include <winuser.h>
1RT_MANIFEST"$(_VC_MANIFEST_BASENAME).auto.manifest"
<< KEEP

$(_VC_MANIFEST_BASENAME).auto.manifest :
    type <<$@
<?xml version='1.0' encoding='UTF-8' standalone='yes'?>
<assembly xmlns='urn:schemas-microsoft-com:asm.v1' manifestVersion='1.0'>
</assembly>
<< KEEP

# end of makefile.targ.inc
```

## <a name="see-also"></a>Zobacz też

[Informacje o generowaniu manifestu dla programów C/C++](understanding-manifest-generation-for-c-cpp-programs.md)
