---
title: Błąd kompilatora C3910
ms.date: 11/04/2016
f1_keywords:
- C3910
helpviewer_keywords:
- C3910
ms.assetid: cfcbe620-b463-463b-95ea-2d60ad33ebb5
ms.openlocfilehash: 186cd67d77e9aafbfe6a7d9dc18afb2bdbd94f0c
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/18/2019
ms.locfileid: "59776519"
---
# <a name="compiler-error-c3910"></a>Błąd kompilatora C3910

"event": należy zdefiniować element członkowski "method"

Zdarzenie zostało zdefiniowane, ale nie zawiera metody określonego, wymaganego dostępu.

Aby uzyskać więcej informacji, zobacz [zdarzeń](../../extensions/event-cpp-component-extensions.md).

Poniższy przykład spowoduje wygenerowanie C3910:

```
// C3910.cpp
// compile with: /clr /c
delegate void H();
ref class X {
   event H^ E {
      // uncomment the following lines
      // void add(H^) {}
      // void remove( H^ h ) {}
      // void raise( ) {}
   };   // C3910

   event H^ E2; // OK data member
};
```