---
description: 'Dowiedz się więcej na temat: Ostrzeżenie kompilatora C4430'
title: Ostrzeżenie kompilatora C4430
ms.date: 11/04/2016
f1_keywords:
- C4430
helpviewer_keywords:
- C4430
ms.assetid: 12efbfff-aa58-4a86-a7d6-2c6a12d01dd3
ms.openlocfilehash: af214bb0e9d373ee319008f509ba78f5d7ade38b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97344305"
---
# <a name="compiler-warning-c4430"></a>Ostrzeżenie kompilatora C4430

brak specyfikatora typu — zakładany int. Uwaga: C++ nie obsługuje funkcji default-int

Ten błąd może być wygenerowany jako wynik zgodności kompilatora, który został wykonany dla programu Visual Studio 2005: wszystkie deklaracje muszą jawnie określać typ; wartość int nie jest już założono.

C4430 jest zawsze wystawiony jako błąd.  Możesz wyłączyć to ostrzeżenie przy użyciu `#pragma warning` lub **/WD**; zobacz [Ostrzeżenie](../../preprocessor/warning.md) , [/W,/W0,/W1,/W2,/W3,/W4,/W1,/W2,/W3,/W4,/Wall,/WD,/we,/wo,/WV,/WX (poziom ostrzeżenia)](../../build/reference/compiler-option-warning-level.md) , aby uzyskać więcej informacji.

## <a name="example"></a>Przykład

Poniższy przykład generuje C4430.

```cpp
// C4430.cpp
// compile with: /c
struct CMyClass {
   CUndeclared m_myClass;  // C4430
   int m_myClass;  // OK
};

typedef struct {
   POINT();   // C4430
   // try the following line instead
   // int POINT();
   unsigned x;
   unsigned y;
} POINT;
```
