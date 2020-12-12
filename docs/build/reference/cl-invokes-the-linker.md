---
description: 'Dowiedz się więcej o: CL wywołuje konsolidator'
title: CL wywołuje konsolidator
ms.date: 11/04/2016
helpviewer_keywords:
- compiling source code [C++], without linking
- invoking linker from the compiler
- LINK tool [C++], invoking from CL compiler
- cl.exe compiler [C++], compiling without linking
- cl.exe compiler [C++], controlling linker
ms.assetid: eae47ef7-09eb-40c9-b318-7c714cd452fc
ms.openlocfilehash: ddd693cdba625756b8085d2f8cb3870d8cdc6add
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97179164"
---
# <a name="cl-invokes-the-linker"></a>CL wywołuje konsolidator

CL automatycznie wywołuje konsolidator po skompilowaniu, chyba że jest używana opcja/c. CL przekazuje do konsolidatora nazwy plików. obj utworzonych podczas kompilowania i nazwy innych plików określonych w wierszu polecenia. Konsolidator używa opcji wymienionych w zmiennej środowiskowej LINK. Można użyć opcji/link, aby określić Opcje konsolidatora w wierszu polecenia CL. Opcje, które przestrzegają opcji/link, zastępują te w zmiennej środowiskowej LINK. Opcje w poniższej tabeli pomijają łączenie.

|Opcja|Opis|
|------------|-----------------|
|/c|Kompiluj bez konsolidacji|
|/E,/EP,/P|Przetwarzanie wstępne bez kompilowania lub łączenia|
|/Zg|Generuj prototypy funkcji|
|/ZS|Sprawdź składnię|

Aby uzyskać więcej informacji na temat łączenia, zobacz [MSVC Opcje konsolidatora](linker-options.md).

## <a name="example"></a>Przykład

Załóżmy, że kompilujesz trzy pliki źródłowe C: MAIN. c, MOD1. c i MOD2. c. Każdy plik zawiera wywołanie funkcji zdefiniowanej w innym pliku:

- MAIN. c wywołuje funkcję `func1` w MOD1. c i funkcję `func2` w MOD2. c.

- MOD1. c wywołuje funkcje biblioteki standardowej `printf_s` i `scanf_s` .

- MOD2. c wywołuje funkcje graficzne o nazwach `myline` i `mycircle` , które są zdefiniowane w bibliotece o nazwie Moja Graf. lib.

Aby skompilować ten program, skompiluj z następującym wierszem polecenia:

```
CL MAIN.c MOD1.C MOD2.C MYGRAPH.lib
```

CL najpierw kompiluje pliki źródłowe C i tworzy pliki obiektów MAIN. obj, MOD1. obj i MOD2. obj. Kompilator umieszcza nazwę biblioteki standardowej w każdym pliku. obj. Aby uzyskać więcej informacji, zobacz [Korzystanie z biblioteki Run-Time](md-mt-ld-use-run-time-library.md).

CL przekazuje nazwy plików. obj wraz z nazwą webgraph. lib do konsolidatora. Konsolidator rozpoznaje odwołania zewnętrzne w następujący sposób:

1. W MAIN. obj odwołanie do `func1` jest rozpoznawane przy użyciu definicji w MOD1. obj; odwołanie do `func2` jest rozpoznawane przy użyciu definicji w MOD2. obj.

1. W MOD1. obj, odwołania do `printf_s` i `scanf_s` są rozwiązane przy użyciu definicji w bibliotece, która znajduje się w elemencie MOD1. obj.

1. W MOD2. obj, odwołania do `myline` i `mycircle` są rozwiązane przy użyciu definicji w elemencie webgraph. lib.

## <a name="see-also"></a>Zobacz też

[Opcje kompilatora MSVC](compiler-options.md)<br/>
[Ustawianie opcji kompilatora](compiler-command-line-syntax.md)
