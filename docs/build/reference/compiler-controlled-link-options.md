---
description: 'Dowiedz się więcej o programie: Compiler-Controlled opcje łącza'
title: Opcje LINK kontrolowane przez kompilator
ms.date: 11/04/2016
helpviewer_keywords:
- LINK tool [C++], compiler-controlled options
- linker [C++], CL compiler control
- linking [C++], affected by CL features
- cl.exe compiler [C++], features that affect linking
- cl.exe compiler [C++], controlling linker
ms.assetid: e4c03896-c99c-4599-8502-e0f4bebe69d0
ms.openlocfilehash: 86f03f53fe19f6788528dca421fb6030289fca99
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97178982"
---
# <a name="compiler-controlled-link-options"></a>Opcje LINK kontrolowane przez kompilator

Kompilator CL automatycznie wywołuje LINK, chyba że określisz opcję/c. CL zapewnia kontrolę nad konsolidatorem za pomocą opcji wiersza polecenia i argumentów. Poniższa tabela zawiera podsumowanie funkcji w CL, które mają wpływ na łączenie.

|Specyfikacja CL|Działanie CL, które ma wpływ na LINK|
|----------------------|---------------------------------|
|Każde rozszerzenie nazwy pliku inne niż. c,. cxx,. cpp lub. def|Przekazuje nazwę pliku jako dane wejściowe do LINKu|
|*filename*. def|Przekazuje/DEF:*filename*. def|
|*Liczba* /f|Passs/STACK:*Number*|
|*Nazwa pliku* /FD|Przekazuje/PDB:*filename*|
|*Nazwa pliku* /Fe|Przekazuje/OUT:*filename*|
|*Nazwa pliku* /FM|Przekazuje/MAP:*filename*|
|/Gy|Tworzy spakowane funkcje (COMDAT); Włącza łączenie na poziomie funkcji|
|/LD|Passs/DLL|
|/LDd|Passs/DLL|
|/link|Przekazuje pozostałą część wiersza polecenia, aby połączyć|
|/MD lub/MT|Umieszcza domyślną nazwę biblioteki w pliku. obj|
|/MDd lub/MTd|Umieszcza domyślną nazwę biblioteki w pliku. obj. Definiuje symbol **_DEBUG**|
|/nologo|Passs/NOLOGO|
|/Zd|Passs/DEBUG|
|/Zi lub/Z7|Passs/DEBUG|
|/Zl|Pomija domyślną nazwę biblioteki z pliku. obj|

Aby uzyskać więcej informacji, zobacz [Opcje kompilatora MSVC](compiler-options.md).

## <a name="see-also"></a>Zobacz też

[Dokumentacja konsolidatora MSVC](linking.md)<br/>
[MSVC Opcje konsolidatora](linker-options.md)
