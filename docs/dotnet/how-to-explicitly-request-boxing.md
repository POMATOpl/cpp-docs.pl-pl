---
title: 'Porady: jawne żądanie konwersji boxing'
ms.date: 11/04/2016
helpviewer_keywords:
- boxing, explicitly requesting
ms.assetid: 1359e6e5-162d-4f5d-9b6a-1690d93df3ee
ms.openlocfilehash: ae0d26157bce1892888ea64d953d4c020c0bec87
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/31/2018
ms.locfileid: "50636335"
---
# <a name="how-to-explicitly-request-boxing"></a>Porady: jawne żądanie konwersji boxing

Możesz jawne żądanie konwersji boxing, przypisując zmienną do zmiennej typu `Object`.

## <a name="example"></a>Przykład

```
// vcmcppv2_explicit_boxing3.cpp
// compile with: /clr
using namespace System;

void f(int i) {
   Console::WriteLine("f(int i)");
}

void f(Object ^o) {
   Console::WriteLine("f(Object^ o)");
}

int main() {
   int i = 5;
   Object ^ O = i;   // forces i to be boxed
   f(i);
   f(O);
   f( (Object^)i );  // boxes i
}
```

```Output
f(int i)
f(Object^ o)
f(Object^ o)
```

## <a name="see-also"></a>Zobacz też

[Konwersja boxing](../windows/boxing-cpp-component-extensions.md)