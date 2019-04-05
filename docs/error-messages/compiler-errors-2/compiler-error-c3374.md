---
title: Błąd kompilatora C3374
ms.date: 11/04/2016
f1_keywords:
- C3374
helpviewer_keywords:
- C3374
ms.assetid: 41431299-bd20-47d4-a0c8-1334dd79018b
ms.openlocfilehash: 4b00b1cea8ac462c82c11d9f5b207706af74959c
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/05/2019
ms.locfileid: "59022635"
---
# <a name="compiler-error-c3374"></a>Błąd kompilatora C3374

Nie można przyjąć adresu "function", chyba że podczas tworzenia wystąpienia delegata

Adres funkcji została wykonana w kontekście innej niż tworzenia wystąpienia delegata.

Poniższy przykład spowoduje wygenerowanie C3374:

```
// C3374.cpp
// compile with: /clr
public delegate void MyDel(int i);

ref class A {
public:
   void func1(int i) {
      System::Console::WriteLine("in func1 {0}", i);
   }
};

int main() {
   &A::func1;   // C3374

   // OK
   A ^ a = gcnew A;
   MyDel ^ StaticDelInst = gcnew MyDel(a, &A::func1);
}
```

## <a name="see-also"></a>Zobacz także

[Instrukcje: Definiowanie i korzystanie z obiektów delegowanych (C + +/ CLI)](../../dotnet/how-to-define-and-use-delegates-cpp-cli.md)