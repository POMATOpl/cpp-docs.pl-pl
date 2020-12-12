---
description: 'Dowiedz się więcej na temat: błąd matematyczny matematyczny m6111'
title: Błąd matematyczny M6111
ms.date: 11/04/2016
f1_keywords:
- M6111
helpviewer_keywords:
- M6111
ms.assetid: c0fc13f8-33c8-4e3f-a440-126cc623441b
ms.openlocfilehash: 9bf2d620a0df18752b74aaacd4d2415510407f0f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97244345"
---
# <a name="math-error-m6111"></a>Błąd matematyczny M6111

Niedopełnienie stosu

Operacja zmiennoprzecinkowa spowodowała Niedopełnienie stosu na współprocesorze 8087/287/387 lub w emulatorze.

Ten błąd jest często spowodowany wywołaniem **`long double`** funkcji, która nie zwraca wartości. Na przykład poniższy generuje ten błąd podczas kompilowania i uruchamiania:

```
long double ld() {};
main ()
{
  ld();
}
```

Program kończy pracę z kodem zakończenia 139.
