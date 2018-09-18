---
title: Błąd kompilatora C3915 | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3915
dev_langs:
- C++
helpviewer_keywords:
- C3915
ms.assetid: 2b0a5e5f-3aec-4a4b-9157-233031817084
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1e34ad9c292f79bb29684d0984fb7e504dfafa23
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/18/2018
ms.locfileid: "46051675"
---
# <a name="compiler-error-c3915"></a>Błąd kompilatora C3915

"type" nie ma domyślnie indeksowanej właściwości (klasa indeksatora)

Typ nie ma domyślnych, indeksowanej właściwości.

Aby uzyskać więcej informacji, zobacz [właściwość](../../windows/property-cpp-component-extensions.md).

## <a name="example"></a>Przykład

Poniższy przykład spowoduje wygenerowanie C3915.

```
// C3915.cpp
// compile with: /clr
ref class X {
public:
// uncomment property to resolve this C3915
//   property int default[]
//   {
//      int get(int i)
//      {
//         return 863;
//      }
//   }
};

int main() {
   X^ x = new X;
   System::Console::WriteLine(x[1]);   // C3915
}
```

## <a name="example"></a>Przykład

C3915 może również wystąpić, jeśli użytkownik podejmie próbę konsumowanie indeksatora domyślny, w tym samym compiland —, gdzie został zdefiniowany z użyciem <xref:System.Reflection.DefaultMemberAttribute>.

Poniższy przykład spowoduje wygenerowanie C3915.

```
// C3915_b.cpp
// compile with: /clr
using namespace System;

[Reflection::DefaultMember("XXX")]
ref struct A {
   property Double XXX[Double] {
      Double get(Double data) {
         return data*data;
      }
   }
};

ref struct B {
   property Double default[Double] {
      Double get(Double data) {
         return data*data;
      }
   }
};

int main() {
   A ^ mya = gcnew A();
   Console::WriteLine("{0}", mya[3]);   // C3915

   B ^ myb = gcnew B();
   Console::WriteLine("{0}", myb[3]);   // OK
}
```