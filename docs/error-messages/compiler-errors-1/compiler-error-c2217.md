---
description: 'Dowiedz się więcej o: błąd kompilatora C2217'
title: Błąd kompilatora C2217
ms.date: 11/04/2016
f1_keywords:
- C2217
helpviewer_keywords:
- C2217
ms.assetid: 1ce1e3f5-4171-4376-804d-967f7e612935
ms.openlocfilehash: 4cd67cb56cb988aa005725435f1829312ee57a31
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97245541"
---
# <a name="compiler-error-c2217"></a>Błąd kompilatora C2217

element "Attribute1" wymaga "attribute2"

Pierwszy atrybut funkcji wymaga drugiego atrybutu.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Aby rozwiązać ten problem, sprawdzając następujące możliwe przyczyny

1. Funkcja Interrupt ( `__interrupt` ) została zadeklarowana jako `near` . Funkcje przerwania muszą być `far` .

1. Funkcja Interrupt została zadeklarowana z **`__stdcall`** , lub **`__fastcall`** . Funkcje przerwania muszą używać konwencji wywoływania języka C.

## <a name="example"></a>Przykład

C2217 może również wystąpić, jeśli podejmiesz próbę powiązania delegata z funkcją CLR, która przyjmuje zmienną liczbę argumentów. Jeśli funkcja ma także Przeciążenie tablic parametrów, zamiast tego użyj. Poniższy przykład generuje C2217.

```cpp
// C2217.cpp
// compile with: /clr
using namespace System;
delegate void MyDel(String^, Object^, Object^, ...);   // C2217
delegate void MyDel2(String ^, array<Object ^> ^);   // OK

int main() {
   MyDel2^ wl = gcnew MyDel2(Console::WriteLine);
   array<Object ^ > ^ x = gcnew array<Object ^>(2);
   x[0] = safe_cast<Object^>(0);
   x[1] = safe_cast<Object^>(1);

   // wl("{0}, {1}", 0, 1);
   wl("{0}, {1}", x);
}
```
