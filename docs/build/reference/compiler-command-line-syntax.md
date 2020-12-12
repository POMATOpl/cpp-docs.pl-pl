---
description: Dowiedz się więcej o składni Command-Line kompilatora
title: Składnia Command-Line kompilatora MSVC
ms.date: 11/04/2016
helpviewer_keywords:
- syntax, CL compiler command line
- cl.exe compiler, command-line syntax
ms.assetid: acba2c1c-0803-4a3a-af25-63e849b930a2
ms.openlocfilehash: 91340aa543f0e79d3071b93921742b8147918b2e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97182219"
---
# <a name="compiler-command-line-syntax"></a>Składnia wiersza polecenia kompilatora

W wierszu polecenia CL jest stosowana następująca składnia:

```
CL [option...] file... [option | file]... [lib...] [@command-file] [/link link-opt...]
```

W poniższej tabeli opisano dane wejściowe polecenia CL.

|Wpis|Znaczenie|
|-----------|-------------|
|*zaznaczyć*|Co najmniej jedna [opcja CL](compiler-options.md). Należy pamiętać, że wszystkie opcje mają zastosowanie do wszystkich określonych plików źródłowych. Opcje są określone za pomocą ukośnika (/) lub kreski (-). Jeśli opcja przyjmuje argument, opis opcji wskazuje, czy spacja jest dozwolona między opcją a argumentami. Nazwy opcji (z wyjątkiem opcji/HELP) uwzględniają wielkość liter. Aby uzyskać więcej informacji [, zobacz kolejność CL](order-of-cl-options.md) .|
|`file`|Nazwa co najmniej jednego pliku źródłowego, pliki obj lub biblioteki. CL kompiluje pliki źródłowe i przekazuje nazwy plików. obj i bibliotek do konsolidatora. Aby uzyskać więcej informacji, zobacz [Składnia nazwy pliku CL](cl-filename-syntax.md) .|
|*lib*|Co najmniej jedna nazwa biblioteki. CL przekazuje te nazwy do konsolidatora.|
|*plik polecenia*|Plik, który zawiera wiele opcji i nazw plików. Więcej informacji można znaleźć w [plikach poleceń CL](cl-command-files.md) .|
|*wybór linku*|Co najmniej jedna [MSVC Opcje konsolidatora](linker-options.md). CL przekazuje te opcje do konsolidatora.|

Można określić dowolną liczbę opcji, nazw plików i bibliotek, tak długo, jak liczba znaków w wierszu polecenia nie przekracza 1024, limit określony przez system operacyjny.

Aby uzyskać informacje na temat wartości zwracanej przez cl.exe, zobacz [zwracaną wartość cl.exe](return-value-of-cl-exe.md) .

> [!NOTE]
> Limit danych wejściowych w wierszu polecenia wynoszący 1024 znaków nie jest gwarantowany w przyszłych wersjach systemu Windows.

## <a name="see-also"></a>Zobacz też

[Opcje kompilatora MSVC](compiler-options.md)
