---
description: 'Dowiedz się więcej na temat: Ostrzeżenie kompilatora C4867'
title: Ostrzeżenie kompilatora C4867
ms.date: 11/04/2016
f1_keywords:
- C4867
helpviewer_keywords:
- C4867
ms.assetid: 8a257d70-c3a7-462d-b285-e57c952a8bf7
ms.openlocfilehash: d9d263c041e12ff985ec5e46eb56a0af99bcf69d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97315026"
---
# <a name="compiler-warning-c4867"></a>Ostrzeżenie kompilatora C4867

"Function": wywołanie funkcji nie ma listy argumentów; Użyj elementu "Call", aby utworzyć wskaźnik do składowej

Nieprawidłowo zainicjowany wskaźnik do funkcji członkowskiej.

To ostrzeżenie może być generowane w wyniku działania kompilatora, który został wykonany dla programu Visual Studio 2005: Ulepszona zgodność wskaźnika do składowej.  Kod, który został skompilowany przed Visual Studio 2005, będzie teraz generował C4867.

To ostrzeżenie jest zawsze emitowane jako błąd. Aby wyłączyć to ostrzeżenie, użyj dyrektywy pragma [ostrzeżenia](../../preprocessor/warning.md) . Aby uzyskać więcej informacji na temat C4867 i MFC/ATL, zobacz [_ATL_ENABLE_PTM_WARNING](../../atl/reference/compiler-options-macros.md#_atl_enable_ptm_warning).

## <a name="example"></a>Przykład

Poniższy przykład generuje C4867.

```cpp
// C4867.cpp
// compile with: /c
class A {
public:
   void f(int) {}

   typedef void (A::*TAmtd)(int);

   struct B {
      TAmtd p;
   };

   void g() {
      B b = {f};   // C4867
      B b2 = {&A::f};   // OK
   }
};
```
