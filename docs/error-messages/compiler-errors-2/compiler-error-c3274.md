---
title: Błąd kompilatora C3274 | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3274
dev_langs:
- C++
helpviewer_keywords:
- C3274
ms.assetid: 1f03f18e-b569-48eb-9249-11c70122a305
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 424b6be69559932ac6f16dc83e39257e414a2120
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/18/2018
ms.locfileid: "46088491"
---
# <a name="compiler-error-c3274"></a>Błąd kompilatora C3274

__finally/finally bez pasującego try

A [__finally](../../cpp/try-finally-statement.md) lub [na koniec](../../dotnet/finally.md) znaleziono instrukcję bez odpowiadającego mu `try`. Aby rozwiązać ten problem, Usuń `__finally` instrukcji lub Dodaj `try` poufności informacji dotyczące `__finally`.

Poniższy przykład spowoduje wygenerowanie C3274:

```
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