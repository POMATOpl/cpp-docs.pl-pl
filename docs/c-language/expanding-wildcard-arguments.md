---
title: Rozszerzanie argumentów z symbolami wieloznacznymi
description: Jak używać opcji konsolidatora do przetwarzania wieloznacznych argumentów wiersza polecenia w programach.
ms.date: 11/20/2020
helpviewer_keywords:
- asterisk wildcard
- question mark, wildcard
- expanding wildcard arguments
- wildcards, expanding
ms.openlocfilehash: b847a5dd8af577a4e30edcd9bc7fc34add296c17
ms.sourcegitcommit: b02c61667ff7f38e7add266d0aabd8463f2dbfa1
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/23/2020
ms.locfileid: "95483311"
---
# <a name="expanding-wildcard-arguments"></a>Rozszerzanie argumentów z symbolami wieloznacznymi

Rozszerzenie argumentu wieloznacznego to specyficzny dla firmy Microsoft.

Po uruchomieniu programu C można użyć jednego z dwóch symboli wieloznacznych, znaku zapytania ( **`?`** ) i gwiazdki ( **`*`** ), aby określić argumenty filename i Path w wierszu polecenia.

Domyślnie symbole wieloznaczne nie są rozwinięte w argumentach wiersza polecenia. Można zastąpić normalną procedurę ładowania wektora argumentu `argv` z wersją, która rozszerza symbole wieloznaczne przez połączenie z *`setargv.obj`* plikiem lub *`wsetargv.obj`* . Jeśli program używa `main` funkcji, Połącz z *`setargv.obj`* . Jeśli program używa `wmain` funkcji, Połącz z *`wsetargv.obj`* . Oba te elementy mają równoważne zachowanie. 

Aby połączyć się z *`setargv.obj`* lub *`wsetargv.obj`* , użyj **`/link`** opcji. Na przykład:

**`cl example.c /link setargv.obj`**

Symbole wieloznaczne są rozwinięte w taki sam sposób, jak polecenia systemu operacyjnego.

## <a name="see-also"></a>Zobacz także

[Opcje łącza](../c-runtime-library/link-options.md)\
[`main` wykonanie funkcji i programu](../c-language/main-function-and-program-execution.md)
