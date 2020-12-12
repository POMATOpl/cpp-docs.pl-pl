---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 1) C4925'
title: Ostrzeżenie kompilatora (poziom 1) C4925
ms.date: 11/04/2016
f1_keywords:
- C4925
helpviewer_keywords:
- C4925
ms.assetid: a4b206c0-016a-4f28-873a-bb8bb41bad50
ms.openlocfilehash: 0fefea9580631439c9e442bb737f39b5c236b229
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97301948"
---
# <a name="compiler-warning-level-1-c4925"></a>Ostrzeżenie kompilatora (poziom 1) C4925

"Method": nie można wywołać metody dispinterface z poziomu skryptu

W językach skryptów nie można utworzyć VT_BYREF parametru "in". można utworzyć tylko parametry VT_BYREF out.

Innym sposobem na rozwiązanie tego ostrzeżenia jest to, że parametr (w definicji i implementacji) nie jest typem wskaźnika.

Poniższy przykład generuje C4925:

```cpp
// C4925.cpp
// compile with: /LD /W1
#define _ATL_ATTRIBUTES 1
#include <atlbase.h>
#include <atlcom.h>
[ module(name="Test")];

[ dispinterface, uuid("00000000-0000-0000-0000-000000000001") ]
__interface IDisp {
   [id(9)] void f([in] int*);
};

[ coclass, uuid("00000000-0000-0000-0000-000000000002")  ]
struct CDisp : IDisp {   // C4925
   void f(int*) {}
};
```
