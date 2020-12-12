---
description: 'Dowiedz się więcej na temat: Module-Definition (. Def) — pliki'
title: Pliki definicji modułu (.Def)
ms.date: 11/04/2016
helpviewer_keywords:
- def files
- module definition files
- .def files
ms.assetid: 08c0bc28-c5d2-47aa-9624-7fc68bcaa4d8
ms.openlocfilehash: d52141a2917b2c82616597b2d070a84b96d1a653
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97137816"
---
# <a name="module-definition-def-files"></a>Pliki definicji modułu (.Def)

Pliki definicji modułów (. def) udostępniają konsolidatorowi informacje o eksportach, atrybutach i innych informacjach o programie, który ma być połączony. Plik. def jest najbardziej przydatny podczas kompilowania biblioteki DLL. Ponieważ istnieją [Opcje konsolidatora MSVC](linker-options.md) , które mogą być używane zamiast instrukcji definicji modułu, pliki. def zazwyczaj nie są konieczne. Można również użyć [__declspec (dllexport)](../exporting-from-a-dll-using-declspec-dllexport.md) jako sposobu określania funkcji eksportowanych.

Można wywołać plik. def podczas fazy konsolidatora przy użyciu opcji konsolidatora [/DEF (Określ plik Module-Definition)](def-specify-module-definition-file.md) .

Jeśli tworzysz plik. exe, który nie ma żadnych eksportów, użycie pliku. def spowoduje powiększenie i wolniejsze ładowanie pliku wyjściowego.

Aby zapoznać się z przykładem, zobacz [Eksportowanie z biblioteki DLL przy użyciu plików DEF](../exporting-from-a-dll-using-def-files.md).

Aby uzyskać więcej informacji, zobacz następujące sekcje:

- [Reguły dla instrukcji Module-Definition](rules-for-module-definition-statements.md)

- [Eksportowanie](exports.md)

- [HEAPSIZE](heapsize.md)

- [BIBLIOTEKA](library.md)

- [NAZWA](name-c-cpp.md)

- [POSZCZEGÓLNE](sections-c-cpp.md)

- [STACKSIZE](stacksize.md)

- [STUB](stub.md)

- [Wersja](version-c-cpp.md)

- [Słowa zastrzeżone](reserved-words.md)

## <a name="see-also"></a>Zobacz też

[Odwołanie kompilacji C/C++](c-cpp-building-reference.md)<br/>
[MSVC Opcje konsolidatora](linker-options.md)
