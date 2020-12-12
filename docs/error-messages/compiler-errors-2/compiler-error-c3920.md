---
description: 'Dowiedz się więcej o: błąd kompilatora C3920'
title: Błąd kompilatora C3920
ms.date: 11/04/2016
f1_keywords:
- C3920
helpviewer_keywords:
- C3920
ms.assetid: 66e91f28-ed82-4ce2-bf22-c0c74905b1ed
ms.openlocfilehash: b4cb793744126ee7bc91d18692d25439880fc672
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97326576"
---
# <a name="compiler-error-c3920"></a>Błąd kompilatora C3920

"operator" ": nie można zdefiniować przyrostkowego przyrostu/zmniejszania WinRT lub operatora CLR wywołującego przyrostowy operator WinRT lub CLR wywoła odpowiadający mu prefiks WinRT lub CLR (op_Increment/op_Decrement), ale z semantyką przyrostkową

Środowisko wykonawcze systemu Windows i CLR nie obsługują operatora przyrostkowego i operatory przyrostkowe zdefiniowane przez użytkownika są niedozwolone.  Można zdefiniować operator prefiksu i operator prefiksu będzie używany dla operacji poprzedzających i po przyrost.

Poniższy przykład generuje C3920 i pokazuje, jak to naprawić:

```cpp
// C3920.cpp
// compile with: /clr /LD
public value struct V {
   static V operator ++(V me, int)
   // try the following line instead
   // static V operator ++(V me)
   {   // C3920
      me.m_i++;
      return me;
   }

   int m_i;
};
```
