---
description: 'Dowiedz się więcej o: błąd kompilatora C2004'
title: Błąd kompilatora C2004
ms.date: 11/04/2016
f1_keywords:
- C2004
helpviewer_keywords:
- C2004
ms.assetid: d81526dd-3a00-4593-87b0-d910d3d29bca
ms.openlocfilehash: f418d2c2c372b228cc50b82237d8ebc56321e2c7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340388"
---
# <a name="compiler-error-c2004"></a>Błąd kompilatora C2004

Oczekiwano instrukcji "defined (ID)"

Identyfikator musi występować w nawiasach po słowie kluczowym preprocesora.

Ten błąd może być również wygenerowany w wyniku działania kompilatora, który został wykonany dla programu Visual Studio .NET 2003: brak nawiasu w dyrektywie preprocesora. Jeśli brakuje nawiasu zamykającego w dyrektywie preprocesora, kompilator wygeneruje błąd.

## <a name="examples"></a>Przykłady

Poniższy przykład generuje C2004:

```cpp
// C2004.cpp
// compile with: /DDEBUG
#include <stdio.h>

int main()
{
    #if defined(DEBUG   // C2004
        printf_s("DEBUG defined\n");
    #endif
}
```

Możliwe rozwiązanie:

```cpp
// C2004b.cpp
// compile with: /DDEBUG
#include <stdio.h>

int main()
{
    #if defined(DEBUG)
        printf_s("DEBUG defined\n");
    #endif
}
```
