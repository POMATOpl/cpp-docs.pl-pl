---
title: Błąd kompilatora C3272
ms.date: 11/04/2016
f1_keywords:
- C3272
helpviewer_keywords:
- C3272
ms.assetid: 7cdf254d-f207-4116-a1bf-7386f3b82a6f
ms.openlocfilehash: 14eefa303a8148b79ca7bc0d1777688ffce176f1
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/03/2019
ms.locfileid: "74753851"
---
# <a name="compiler-error-c3272"></a>Błąd kompilatora C3272

"symbol": symbol wymaga FieldOffset, ponieważ jest elementem członkowskim typu typename zdefiniowanym z StructLayout (LayoutKind:: Explicit)

Gdy `StructLayout(LayoutKind::Explicit)` obowiązuje, pola muszą być oznaczone `FieldOffset`.

Poniższy przykład generuje C3272:

```cpp
// C3272_2.cpp
// compile with: /clr /c
using namespace System;
using namespace System::Runtime::InteropServices;

[StructLayout(LayoutKind::Explicit)]
ref struct X
{
   int data_;   // C3272
   // try the following line instead
   // [FieldOffset(0)] int data_;
};
```
