---
description: 'Dowiedz się więcej o: błąd kompilatora C3719'
title: Błąd kompilatora C3719
ms.date: 11/04/2016
f1_keywords:
- C3719
helpviewer_keywords:
- C3719
ms.assetid: d0d59d4e-babb-4480-9ef7-70cf1a28165c
ms.openlocfilehash: a05e6cf7ee1aa67f3e8aa3e1fab737b9f5bc2969
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97239080"
---
# <a name="compiler-error-c3719"></a>Błąd kompilatora C3719

"Interface": Źródło zdarzeń oparte na interfejsie może być używane tylko dla zdarzeń COM

Zadeklarowano interfejs w kontekście innym niż COM.

Poniższy przykład generuje C3719:

```cpp
// C3719a.cpp
#define _ATL_ATTRIBUTES 1
#include "atlbase.h"
#include "atlcom.h"

[module(name="MyLibrary", version="1.2", helpfile="MyHelpFile")];

[object]
__interface I {
   HRESULT func1();
};

[event_source(native), coclass]
struct A {
   __event __interface I;   // C3719

   // try the following line instead
   // __event func2();
};

int main() {
}
```

Aby naprawić ten błąd, należy odpowiednio zastosować atrybuty [Object](../../windows/attributes/object-cpp.md), [coclass](../../windows/attributes/coclass.md), [event_source](../../windows/attributes/event-source.md)i [event_receiver](../../windows/attributes/event-receiver.md) , aby uczynić klasy, w których są używane klasy interfejsów com. Na przykład:

```cpp
// C3719b.cpp
#define _ATL_ATTRIBUTES 1
#include <atlbase.h>
#include <atlcom.h>

[module(name="xx")];
[object, uuid("00000000-0000-0000-0000-000000000001")]
__interface I {
   HRESULT f();
};

[coclass, event_source(com) , uuid("00000000-0000-0000-0000-000000000002")]
struct MyStruct {
   __event __interface I;
};

[event_receiver(com)]
struct MyStruct2 {
   void f() {
   }
   MyStruct2(I* pB) {
      __hook(&I::f, pB, &MyStruct2::f);
   }
};

int main()
{
}
```
