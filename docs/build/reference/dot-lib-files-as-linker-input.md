---
description: Dowiedz się więcej na temat:. Pliki lib jako dane wejściowe konsolidatora
title: Pliki .Lib — Wejście konsolidatora
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.AdditionalDependencies
helpviewer_keywords:
- OMF libraries
- linking [C++], OMF libraries
- import libraries, linker files
- libraries [C++], .lib files as linker input
- COFF files, import libraries
- default libraries [C++], linker output
- default libraries [C++]
- defaults [C++], libraries
- .lib files
ms.assetid: dc5d2b1c-2487-41fa-aa71-ad1e0647958b
ms.openlocfilehash: f4a3b6c6487947772fb72135fb26f67857f0937e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97201264"
---
# <a name="lib-files-as-linker-input"></a>Pliki .Lib — Wejście konsolidatora

LINK akceptuje biblioteki standardowe COFF i biblioteki importu COFF, które zwykle mają rozszerzenie lib. Biblioteki standardowe zawierają obiekty i są tworzone za pomocą narzędzia LIB. Biblioteki importowane zawierają informacje o eksportach w innych programach i są tworzone przez LINK podczas kompilowania programu zawierającego eksporty lub narzędzia LIB. Aby uzyskać informacje na temat tworzenia bibliotek standardowych lub importowanych przy użyciu biblioteki LIB, zobacz [Dokumentacja biblioteki lib](lib-reference.md). Aby uzyskać szczegółowe informacje na temat używania LINKu do tworzenia biblioteki importu, zobacz [/dll](dll-build-a-dll.md) opcji.

Biblioteka jest określona do łączenia jako argument nazwy pliku lub biblioteki domyślnej. LINK rozwiązuje odwołania zewnętrzne przez wyszukanie najpierw w bibliotekach określonych w wierszu polecenia, a następnie w bibliotekach domyślnych określonych przy użyciu opcji [/DEFAULTLIB](defaultlib-specify-default-library.md) , a następnie w bibliotekach domyślnych o nazwach w plikach. obj. Jeśli ścieżka jest określona za pomocą nazwy biblioteki, LINK szuka biblioteki w tym katalogu. Jeśli ścieżka nie zostanie określona, LINK najpierw znajduje się w katalogu, z którego łączy, a następnie w dowolnych katalogach określonych w zmiennej środowiskowej LIB.

## <a name="to-add-lib-files-as-linker-input-in-the-development-environment"></a>Aby dodać pliki lib jako dane wejściowe konsolidatora w środowisku programistycznym

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać szczegółowe informacje, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Wybierz stronę właściwości **danych wejściowych** w folderze **konsolidatora** .

1. Zmodyfikuj właściwość **dodatkowe zależności** , aby dodać pliki. lib.

## <a name="to-programmatically-add-lib-files-as-linker-input"></a>Aby programowo dodać pliki lib jako dane wejściowe konsolidatora

- Zobacz [AdditionalDependencies](/dotnet/api/microsoft.visualstudio.vcprojectengine.vclinkertool.additionaldependencies).

## <a name="example"></a>Przykład

Poniższy przykład pokazuje, jak skompilować plik. lib i korzystać z niego. Najpierw Skompiluj plik. lib:

```cpp
// lib_link_input_1.cpp
// compile by using: cl /LD lib_link_input_1.cpp
__declspec(dllexport) int Test() {
   return 213;
}
```

Następnie Skompiluj ten przykład przy użyciu utworzonego właśnie pliku lib:

```cpp
// lib_link_input_2.cpp
// compile by using: cl /EHsc lib_link_input_1.lib lib_link_input_2.cpp
__declspec(dllimport) int Test();
#include <iostream>
int main() {
   std::cout << Test() << std::endl;
}
```

```Output
213
```

## <a name="see-also"></a>Zobacz też

[Połącz pliki wejściowe](link-input-files.md)<br/>
[MSVC Opcje konsolidatora](linker-options.md)
