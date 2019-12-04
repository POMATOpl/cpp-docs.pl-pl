---
title: Błąd kompilatora C2392
ms.date: 11/04/2016
f1_keywords:
- C2392
helpviewer_keywords:
- C2392
ms.assetid: 98ced473-6383-46ed-b79c-21857d65dcb2
ms.openlocfilehash: 15fa4a19cdd791ddb3636f30a636cc084bdc4a5f
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/03/2019
ms.locfileid: "74745008"
---
# <a name="compiler-error-c2392"></a>Błąd kompilatora C2392

"Metoda1": typy zwracanych typów nie są obsługiwane w zarządzanych lub WinRTtypes, w przeciwnym razie "method2" zostałyby przesłonięte

Typy zwrotne typu "Variant" są niedozwolone dla środowisko wykonawcze systemu Windows funkcji Członkowskich lub kompilowania z użyciem opcji [/CLR (Kompilacja środowiska uruchomieniowego języka wspólnego)](../../build/reference/clr-common-language-runtime-compilation.md) .

## <a name="example"></a>Przykład

Poniższy przykład generuje C2392 i pokazuje, jak rozwiązać ten problem.

```cpp
// C2392.cpp
// compile with: /clr
public ref struct B {
public:
   int i;
};

public ref struct D: public B{};

public ref struct B1 {
public:
   virtual B^ mf() {
      B^ pB = gcnew B;
      pB->i = 11;
      return pB;
   }
};

public ref struct D1: public B1 {
public:
   virtual D^ mf() override {  // C2392
   // try the following line instead
   // virtual B^ mf() override {
   // return type D^ is covariant with B^, not allowed with CLR types
      D^ pD = gcnew D;
      pD->i = 12;
      return pD;
   }
};

int main() {
   B1^ pB1 = gcnew D1;
   B^ pB = pB1->mf();
   D^ pD = dynamic_cast<D^>(pB);
}
```
