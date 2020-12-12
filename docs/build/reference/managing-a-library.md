---
description: Dowiedz się więcej na temat zarządzania biblioteką
title: Zarządzanie biblioteką
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLibrarianTool.OVERWRITEAllDefaultLibraries
- VC.Project.VCLibrarianTool.AdditionalDependencies
- VC.Project.VCLibrarianTool.RemoveObjects
- VC.Project.VCLibrarianTool.LibraryPaths
- VC.Project.VCLibrarianTool.OutputFile
- VC.Project.VCLibrarianTool.OVERWRITEDefaultLibraryNames
- VC.Project.VCLibrarianTool.AdditionalLibraryDirectories
- VC.Project.VCLibrarianTool.ListContentsFile
- VC.Project.VCLibrarianTool.ListContents
- VC.Project.VCLibrarianTool.SubSystemVersion
- VC.Project.VCLibrarianTool.OVERWRITEDefaultLibraryName
- VC.Project.VCLibrarianTool.SubSystem
helpviewer_keywords:
- /LIBPATH library manager option
- OUT library manager option
- CONVERT library manager option
- LIBPATH library manager option
- /LIST library manager option
- object files, building and modifying
- -LINK50COMPAT library manager option
- REMOVE library manager option
- SUBSYSTEM library manager option
- /LINK50COMPAT library manager option
- /OUT library manager option
- LIB [C++], managing COFF libraries
- -CONVERT library manager option
- LINK50COMPAT library manager option
- -OUT library manager option
- -REMOVE library manager option
- -LIST library manager option
- /SUBSYSTEM library manager option
- -SUBSYSTEM library manager option
- /REMOVE library manager option
- -LIBPATH library manager option
- object files
- LIST library manager option
- /CONVERT library manager option
ms.assetid: f56a8b85-fbdc-4c09-8d8e-00f0ffe1da53
ms.openlocfilehash: f862dfd460bb51cdf6e855c87b08b7426a5642d0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97199132"
---
# <a name="managing-a-library"></a>Zarządzanie biblioteką

Domyślnym trybem LIB jest Kompilowanie lub modyfikowanie biblioteki obiektów COFF. LIB działa w tym trybie, jeśli nie określisz elementu/EXTRACT (w celu skopiowania obiektu do pliku) lub/DEF (w celu utworzenia biblioteki importu).

Aby skompilować bibliotekę z obiektów i/lub bibliotek, należy użyć następującej składni:

```
LIB [options...] files...
```

To polecenie tworzy bibliotekę z jednego lub więcej *plików* wejściowych. *Pliki* mogą być plikami obiektów COFF, 32-bitowymi plikami obiektów OMF lub istniejącymi bibliotekami COFF. LIB tworzy jedną bibliotekę, która zawiera wszystkie obiekty w określonych plikach. Jeśli plik wejściowy jest 32-bitowym plikiem obiektu OMF, LIB konwertuje go na COFF przed skompilowaniem biblioteki. Biblioteka LIB nie może akceptować 32-bitowego obiektu OMF, który znajduje się w bibliotece utworzonej przez 16-bitową wersję biblioteki LIB. Aby wyodrębnić obiekt, należy najpierw użyć biblioteki 16-bitowej. następnie można użyć wyodrębnionego pliku obiektu jako dane wejściowe do biblioteki 32-bitowej.

Domyślnie LIB nazywa plik wyjściowy przy użyciu podstawowej nazwy pierwszego obiektu lub pliku biblioteki i rozszerzenia. lib. Plik wyjściowy zostanie umieszczony w bieżącym katalogu. Jeśli istnieje już plik o tej samej nazwie, plik wyjściowy zastępuje istniejący plik. Aby zachować istniejącą bibliotekę, użyj opcji/OUT, aby określić nazwę pliku wyjściowego.

Następujące opcje dotyczą tworzenia i modyfikowania biblioteki:

**/LIBPATH:** *dir*<br/>
Zastępuje ścieżkę biblioteki środowiska. Aby uzyskać szczegółowe informacje, zobacz opis opcji LINK [/LIBPATH](libpath-additional-libpath.md) .

**/LIST**<br/>
Wyświetla informacje o bibliotece wyjściowej do wyjścia standardowego. Dane wyjściowe można przekierować do pliku. Można użyć/LIST, aby określić zawartość istniejącej biblioteki bez jej modyfikowania.

**/Name:** *filename*<br/>
Podczas kompilowania biblioteki importowanej, określa nazwę biblioteki DLL, dla której jest tworzona biblioteka importu.

**/NODEFAULTLIB**<br/>
Usuwa co najmniej jedną domyślną bibliotekę z listy bibliotek przeszukiwanych podczas rozpoznawania odwołań zewnętrznych. Aby uzyskać więcej informacji, zobacz [/NODEFAULTLIB](nodefaultlib-ignore-libraries.md) .

**/Out:** *filename*<br/>
Przesłania domyślną nazwę pliku wyjściowego. Domyślnie Biblioteka wyjściowa jest tworzona w bieżącym katalogu, z nazwą podstawową pierwszej biblioteki lub pliku obiektu w wierszu polecenia i rozszerzeniu. lib.

**/Remove:** *obiekt*<br/>
Pomija określony *obiekt* z biblioteki wyjściowej. LIB tworzy bibliotekę wyjściową, łącząc wszystkie obiekty (w plikach lub bibliotekach obiektów), a następnie usuwając wszystkie obiekty określone za pomocą/REMOVE.

**/SUBSYSTEM:**{**CONSOLE** &#124; **EFI_APPLICATION** &#124; **EFI_BOOT_SERVICE_DRIVER** &#124; **EFI_ROM** &#124; **EFI_RUNTIME_DRIVER** &#124; **Native** &#124; **POSIX** &#124; **Windows** &#124; **WindowsCE**} [, # [. # #]]<br/>
Informuje system operacyjny, jak uruchomić program utworzony przez połączenie z biblioteką wyjściową. Aby uzyskać więcej informacji, zobacz opis opcji LINK [/Subsystem](subsystem-specify-subsystem.md) .

W przypadku opcji LIB określonych w wierszu polecenia nie jest rozróżniana wielkość liter.

Za pomocą LIB można wykonać następujące zadania zarządzania biblioteką:

- Aby dodać obiekty do biblioteki, określ nazwę pliku dla istniejącej biblioteki i nazwę pliku dla nowych obiektów.

- Aby połączyć biblioteki, określ nazwy plików biblioteki. Można dodawać obiekty i łączyć biblioteki za pomocą jednego polecenia LIB.

- Aby zastąpić element członkowski biblioteki nowym obiektem, Określ bibliotekę zawierającą obiekt członkowski do zamienienia i nazwę pliku dla nowego obiektu (lub biblioteki, która go zawiera). Gdy obiekt, który ma taką samą nazwę, istnieje w więcej niż jednym pliku wejściowym, LIB umieszcza ostatni obiekt określony w LIB polecenie w bibliotece wyjściowej. Podczas zastępowania elementu członkowskiego biblioteki należy pamiętać o określeniu nowego obiektu lub biblioteki po bibliotece zawierającej stary obiekt.

- Aby usunąć element członkowski z biblioteki, użyj opcji/REMOVE. LIB przetwarza wszystkie specyfikacje/REMOVE po połączeniu wszystkich obiektów wejściowych, niezależnie od kolejności wiersza polecenia.

> [!NOTE]
> Nie można usunąć elementu członkowskiego i wyodrębnić go do pliku w tym samym kroku. Najpierw należy wyodrębnić Obiekt członkowski za pomocą elementu/EXTRACT, a następnie ponownie uruchomić LIB przy użyciu/REMOVE. To zachowanie różni się od wersji 16-bitowej biblioteki (dla bibliotek OMF) udostępnianej w innych produktach firmy Microsoft.

## <a name="see-also"></a>Zobacz też

[Dokumentacja biblioteki LIB](lib-reference.md)
