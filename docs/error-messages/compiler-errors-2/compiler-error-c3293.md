---
title: Błąd kompilatora C3293
ms.date: 07/21/2017
f1_keywords:
- C3293
helpviewer_keywords:
- C3293
ms.assetid: b772cf98-52e0-4e24-be23-1f5d87d999ac
ms.openlocfilehash: 1713632d21ef401fb1177350c81a4a64ed0503ec
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/03/2019
ms.locfileid: "74760117"
---
# <a name="compiler-error-c3293"></a>Błąd kompilatora C3293

"akcesor": Użyj "default", aby uzyskać dostęp do domyślnej właściwości (indeksator) dla klasy "Type"

Właściwość indeksowana była dostępna nieprawidłowo.  Aby uzyskać więcej informacji [, zobacz jak C++: Używanie właściwości w/CLI](../../dotnet/how-to-use-properties-in-cpp-cli.md) .

**Program Visual studio 2017 lub nowszy**: w programie visual Studio 2015 i starszych kompilator w niektórych przypadkach nie znalazł domyślnej właściwości jako indeksatora domyślnego. Można obejść ten problem, używając identyfikatora "default", aby uzyskać dostęp do właściwości. Samo obejście stało się problematyczne po wprowadzeniu domyślnego jako słowa kluczowego w języku C++ 11. W związku z tym w programie Visual Studio 2017 błędy, które wymagały obejścia, zostały naprawione i kompilator zgłasza błąd, gdy wartość domyślna jest używana w celu uzyskania dostępu do domyślnej właściwości klasy.

## <a name="example"></a>Przykład

Poniższy przykład generuje C3293 w programie Visual Studio 2015 i jego wcześniejszych wersjach.

```cpp
// C3293.cpp
// compile with: /clr /c
using namespace System;
ref class IndexerClass {
public:
   // default indexer
   property int default[int] {
      int get(int index) { return 0; }
      void set(int index, int value) {}
   }
};

int main() {
   IndexerClass ^ ic = gcnew IndexerClass;
   ic->Item[0] = 21;   // C3293 in VS2015 OK in VS2017
   ic->default[0] = 21;   // OK in VS2015 and earlier

   String ^s = "Hello";
   wchar_t wc = s->Chars[0];   // C3293 in VS2015 OK in VS2017
   wchar_t wc2 = s->default[0];   // OK in VS2015 and earlier
   Console::WriteLine(wc2);
}
```
