---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 1) C4715'
title: Ostrzeżenie kompilatora (poziom 1) C4715
ms.date: 11/04/2016
f1_keywords:
- C4715
helpviewer_keywords:
- C4715
ms.assetid: 1c819bf7-0d8b-4f5e-b338-9cc292870439
ms.openlocfilehash: 41682beae6e32ba397f3c9dae43d57a182b09b65
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97249103"
---
# <a name="compiler-warning-level-1-c4715"></a>Ostrzeżenie kompilatora (poziom 1) C4715

"Function": nie wszystkie ścieżki sterujące zwracają wartość

Określona funkcja może potencjalnie nie zwracać wartości.

## <a name="example"></a>Przykład

```cpp
// C4715a.cpp
// compile with: /W1 /LD
int func1( int i )
{
   if( i )
   return 3;  // C4715 warning, nothing returned if i == 0
}
```

Aby uniknąć tego ostrzeżenia, zmodyfikuj kod, tak aby wszystkie ścieżki przypisały wartość zwracaną do funkcji:

```cpp
// C4715b.cpp
// compile with: /LD
int func1( int i )
{
   if( i ) return 3;
   else return 0;     // OK, always returns a value
}
```

Istnieje możliwość, że kod może zawierać wywołanie funkcji, która nigdy nie zwraca, jak w poniższym przykładzie:

```cpp
// C4715c.cpp
// compile with: /W1 /LD
void fatal()
{
}
int glue()
{
   if(0)
      return 1;
   else if(0)
      return 0;
   else
      fatal();   // C4715
}
```

Ten kod generuje również ostrzeżenie, ponieważ kompilator nie wie, że nigdy nie `fatal` zwraca. Aby zapobiec generowaniu przez ten kod komunikatu o błędzie, zadeklaruj `fatal` przy użyciu [__declspec (noreturn)](../../cpp/noreturn.md).
