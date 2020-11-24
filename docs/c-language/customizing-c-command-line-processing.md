---
title: Dostosowywanie przetwarzania w wierszu polecenia języka C
description: Jak pominąć `main` funkcję obsługi parametrów w czasie wykonywania w kodzie uruchomienia środowiska uruchomieniowego.
ms.date: 11/19/2020
helpviewer_keywords:
- _spawn functions
- command line, processing
- command-line processing
- startup code, customizing command-line processing
- environment, environment-processing routine
- _setargv function
- command line, processing arguments
- suppressing environment processing
- _exec function
ms.openlocfilehash: fc306172491cd401caeecb3c87c0711f8b4ef911
ms.sourcegitcommit: b02c61667ff7f38e7add266d0aabd8463f2dbfa1
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/23/2020
ms.locfileid: "95483298"
---
# <a name="customizing-c-command-line-processing"></a>Dostosowywanie przetwarzania w wierszu polecenia języka C

Jeśli program nie przyjmuje argumentów wiersza polecenia, można pominąć procedurę przetwarzania wiersza polecenia, aby zaoszczędzić niewielką ilość miejsca. Aby pominąć użycie, Dołącz *`noarg.obj`* plik (dla obu `main` i `wmain` ) w **`/link`** opcjach kompilatora lub w **`LINK`** wierszu polecenia.

Podobnie, jeśli nie masz dostępu do tabeli środowiska za pomocą *`envp`* argumentu, możesz pominąć procedurę wewnętrznego przetwarzania środowiska. Aby pominąć użycie, Dołącz *`noenv.obj`* plik (dla obu `main` i `wmain` ) w **`/link`** opcjach kompilatora lub w **`LINK`** wierszu polecenia.

Aby uzyskać więcej informacji na temat uruchamiania opcji konsolidatora środowiska uruchomieniowego, zobacz [Opcje łącza](../c-runtime-library/link-options.md).

Program może wykonywać wywołania do `spawn` lub `exec` z rodziny procedur w bibliotece środowiska uruchomieniowego języka C. W takim przypadku nie należy pomijać procedury przetwarzania środowiska, ponieważ jest ona używana do przekazywania środowiska z procesu nadrzędnego do procesu podrzędnego.

## <a name="see-also"></a>Zobacz także

[`main` wykonanie funkcji i programu](../c-language/main-function-and-program-execution.md)\
[Opcje łącza](../c-runtime-library/link-options.md).
