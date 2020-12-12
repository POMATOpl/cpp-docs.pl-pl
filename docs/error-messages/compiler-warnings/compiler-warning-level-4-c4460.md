---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 4) C4460'
title: Ostrzeżenie kompilatora (poziom 4) C4460
ms.date: 11/04/2016
f1_keywords:
- C4460
helpviewer_keywords:
- C4460
ms.assetid: c97ac1c9-598d-479e-bfff-c993690c4f3d
ms.openlocfilehash: 68f38ad1ad65b27f35b79495bb2edd930c25d732
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334834"
---
# <a name="compiler-warning-level-4-c4460"></a>Ostrzeżenie kompilatora (poziom 4) C4460

Operator WinRT lub CLR "operator" ma parametr zakończony przez odwołanie. Operator WinRT lub CLR ma inną semantykę z operatora C++ "operator", czy chodziło o wartość?

Wartość została przeniesiona przez odwołanie do zdefiniowanej przez użytkownika środowisko wykonawcze systemu Windows lub operatora CLR. Jeśli wartość zostanie zmieniona wewnątrz funkcji, należy pamiętać, że wartość zwracana po wywołaniu funkcji zostanie przypisana wartość zwracana funkcji. W standardzie C++, zmieniona wartość jest odzwierciedlona po wywołaniu funkcji.

## <a name="example"></a>Przykład

Poniższy przykład generuje C4460 i pokazuje, jak rozwiązać ten problem.

```cpp
// C4460.cpp
// compile with: /W4 /clr
#include <stdio.h>

public value struct V {
   static V operator ++(V& me) {   // C4460
   // try the following line instead
   // static V operator ++(V me) {

      printf_s(__FUNCSIG__ " called\n");
      V tmp = me;
      me.m_i++;
      return tmp;
   }
   int m_i;
};

int main() {
   V v;
   v.m_i = 0;

   printf_s("%d\n", v.m_i);   // Should print 0
   v++;   // Translates to "v = V::operator ++(v)"
   printf_s("%d\n", v.m_i);   // will print 0, hence the warning
}
```
