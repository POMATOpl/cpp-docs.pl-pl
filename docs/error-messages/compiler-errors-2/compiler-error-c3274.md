---
description: 'Dowiedz się więcej o: błąd kompilatora C3274'
title: Błąd kompilatora C3274
ms.date: 11/04/2016
f1_keywords:
- C3274
helpviewer_keywords:
- C3274
ms.assetid: 1f03f18e-b569-48eb-9249-11c70122a305
ms.openlocfilehash: 6706cc404bd6540aff7aa1afb94ada28249a0ade
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97185742"
---
# <a name="compiler-error-c3274"></a>Błąd kompilatora C3274

__finally/finally bez dopasowania try

Nie znaleziono instrukcji [__finally](../../cpp/try-finally-statement.md) lub [finally](../../dotnet/finally.md) bez dopasowania **`try`** . Aby rozwiązać ten problem, Usuń **`__finally`** instrukcję lub Dodaj **`try`** instrukcję dla elementu **`__finally`** .

Poniższy przykład generuje C3274:

```cpp
// C3274.cpp
// compile with: /clr
// C3274 expected
using namespace System;
int main() {
   try {
      try {
         throw gcnew ApplicationException();
      }
      catch(...) {
         Console::Error->WriteLine(L"Caught an exception");
      }
      finally {
         Console::WriteLine(L"In finally");
      }
   } finally {
      Console::WriteLine(L"In finally");
   }

   // Uncomment the following 3 lines to resolve.
   // try {
   //   throw gcnew ApplicationException();
   // }

   finally {
      Console::WriteLine(L"In finally");
   }
   Console::WriteLine(L"**FAIL**");
}
```
