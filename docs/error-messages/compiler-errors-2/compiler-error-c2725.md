---
description: 'Dowiedz się więcej o: błąd kompilatora C2725'
title: Błąd kompilatora C2725
ms.date: 11/04/2016
f1_keywords:
- C2725
helpviewer_keywords:
- C2725
ms.assetid: 13cd5b1b-e906-4cd8-9b2b-510d587c665a
ms.openlocfilehash: 92594737bf06095ffb230cac6bb6d233fc6f9307
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97155491"
---
# <a name="compiler-error-c2725"></a>Błąd kompilatora C2725

"Exception": nie można zgłosić lub przechwycić obiektu zarządzanego lub WinRT przez wartość lub odwołanie

Typ wyjątku zarządzanego lub WinRT jest niepoprawny.

## <a name="examples"></a>Przykłady

Poniższy przykład generuje C2725 i pokazuje, jak rozwiązać ten problem.

```cpp
// C2725.cpp
// compile with: /clr
ref class R {
public:
   int i;
};

int main() {
   R % r1 = *gcnew R;
   throw r1;   // C2725

   R ^ r2 = gcnew R;
   throw r2;   // OK
}
```

Poniższy przykład generuje C2725 i pokazuje, jak rozwiązać ten problem.

```cpp
// C2725b.cpp
// compile with: /clr
using namespace System;
int main() {
   try {}
   catch( System::Exception%) {}   // C2725
   // try the following line instead
   // catch( System::Exception ^e) {}
}
```
