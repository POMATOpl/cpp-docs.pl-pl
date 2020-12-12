---
description: 'Dowiedz się więcej na temat: błąd matematyczny matematyczny M6201'
title: Błąd matematyczny M6201
ms.date: 11/04/2016
f1_keywords:
- M6201
helpviewer_keywords:
- M6201
ms.assetid: 4041c331-d9aa-4dd4-b565-7dbe0218538c
ms.openlocfilehash: 03588b7eed580b95cb263f6e4d71f5a793f4d392
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97244319"
---
# <a name="math-error-m6201"></a>Błąd matematyczny M6201

"Function": błąd _DOMAIN

Argument danej funkcji znajduje się poza domeną dozwolonych wartości wejściowych tej funkcji.

## <a name="example"></a>Przykład

```
result = sqrt(-1.0)   // C statement
result = SQRT(-1.0)   !  FORTRAN statement
```

Ten błąd wywołuje `_matherr` funkcję z nazwą funkcji, jej argumentami i typem błędu. Można napisać ponownie funkcję, `_matherr` Aby dostosować obsługę określonych błędów matematycznych zmiennoprzecinkowych w czasie wykonywania.
