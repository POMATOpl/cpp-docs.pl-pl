---
title: Błąd matematyczny M6201
ms.date: 11/04/2016
f1_keywords:
- M6201
helpviewer_keywords:
- M6201
ms.assetid: 4041c331-d9aa-4dd4-b565-7dbe0218538c
ms.openlocfilehash: 0b1cd0d3fcd86a2174b19da41176dd97f547a295
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/24/2020
ms.locfileid: "80193709"
---
# <a name="math-error-m6201"></a>Błąd matematyczny M6201

"Function": błąd _DOMAIN

Argument danej funkcji znajduje się poza domeną dozwolonych wartości wejściowych tej funkcji.

## <a name="example"></a>Przykład

```
result = sqrt(-1.0)   // C statement
result = SQRT(-1.0)   !  FORTRAN statement
```

Ten błąd wywołuje funkcję `_matherr` z nazwą funkcji, jej argumentami i typem błędu. Można ponownie napisać funkcję `_matherr`, aby dostosować obsługę określonych błędów matematycznych zmiennoprzecinkowych w czasie wykonywania.
