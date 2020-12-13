---
description: 'Dowiedz się więcej o: błąd kompilatora C2891'
title: Błąd kompilatora C2891
ms.date: 11/04/2016
f1_keywords:
- C2891
helpviewer_keywords:
- C2891
ms.assetid: e12cfb2d-df45-4b0d-b155-c51d17e812fa
ms.openlocfilehash: e546340d0ba035da50dd36b18b870b565b6e1bc9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337437"
---
# <a name="compiler-error-c2891"></a>Błąd kompilatora C2891

"parameter": nie można przyjąć adresu parametru szablonu

Nie można przyjąć adresu parametru szablonu, chyba że jest to element lvalue. Parametry typu nie są lvalues, ponieważ nie mają adresu. Wartości spoza typu na listach parametrów szablonu, które nie są lvalues, również nie mają adresu. Jest to przykładowy kod powodujący błąd kompilatora C2891, ponieważ wartość przeniesiona jako parametr szablonu jest kopią kompilatora argumentu szablonu wygenerowanego przez kompilator.

```
template <int i> int* f() { return &i; }
```

Parametry szablonu, które są lvalues, takie jak typy odwołań, mogą mieć swój adres.

```
template <int& r> int* f() { return &r; }
```

Aby naprawić ten błąd, nie pobieraj adresu parametru szablonu, chyba że jest to element lvalue.
