---
description: 'Dowiedz się więcej na temat: STACKSIZE'
title: STACKSIZE
ms.date: 11/04/2016
f1_keywords:
- STACKSIZE
helpviewer_keywords:
- STACKSIZE .def file statement
ms.assetid: 4d8c79bd-1cb4-4e4d-90f2-b5a7a4d20e7a
ms.openlocfilehash: b5d52bccc09979084b9023d380e86fe90e4def32
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97230344"
---
# <a name="stacksize"></a>STACKSIZE

Ustawia rozmiar stosu w bajtach.

```
STACKSIZE reserve[,commit]
```

## <a name="remarks"></a>Uwagi

Odpowiednikiem sposobu ustawiania stosu jest opcja [przydziały stosu](stack-stack-allocations.md) (/stack). Zapoznaj się z dokumentacją dotyczącą tej opcji, aby uzyskać szczegółowe informacje o *rezerwie* i `commit` argumentach.

Ta opcja nie ma wpływu na biblioteki DLL.

## <a name="see-also"></a>Zobacz też

[Reguły dla instrukcji Module-Definition](rules-for-module-definition-statements.md)
