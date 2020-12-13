---
description: 'Dowiedz się więcej o: błąd kompilatora C3365'
title: Błąd kompilatora C3365
ms.date: 11/04/2016
f1_keywords:
- C3365
helpviewer_keywords:
- C3365
ms.assetid: 875ec3a4-522c-4e3d-9b67-48808b857f6d
ms.openlocfilehash: e25c0b4c53b9a811c863a96baf9555d0bde0bfc7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97335013"
---
# <a name="compiler-error-c3365"></a>Błąd kompilatora C3365

operator "operator": różne operandy typu "type1" i "type2"

Podjęto próbę zredagowania delegatów o różnych typach.  Aby uzyskać więcej informacji na temat delegatów [, zobacz How to: define and use delegats (C++/CLI)](../../dotnet/how-to-define-and-use-delegates-cpp-cli.md) .

## <a name="example"></a>Przykład

Poniższy przykład generuje C3365:

```cpp
// C3365.cpp
// compile with: /clr
delegate void D1();
delegate void D2(int);

ref class R {
public:
   void f(){}
   void g(int){}
};

int main() {
   D1^ d1 = gcnew D1(gcnew R, &R::f);
   D2^ d2 = gcnew D2(gcnew R, &R::g);
   D1^ d3 = gcnew D1(gcnew R, &R::f);

   d1 += d2;   // C3365
   d1 += d3;   // OK
   d1();
}
```
