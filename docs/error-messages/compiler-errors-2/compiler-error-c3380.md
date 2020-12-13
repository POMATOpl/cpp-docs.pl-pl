---
description: 'Dowiedz się więcej o: błąd kompilatora C3380'
title: Błąd kompilatora C3380
ms.date: 11/04/2016
f1_keywords:
- C3380
helpviewer_keywords:
- C3380
ms.assetid: 86f1f4ec-4ad8-4a1a-9b6c-2d9b6129df6b
ms.openlocfilehash: bb633d75d08fdbb902f086b3a4cd6a8a6db1fc69
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334996"
---
# <a name="compiler-error-c3380"></a>Błąd kompilatora C3380

"Class": Nieprawidłowy specyfikator dostępu do zestawu — dozwolone są tylko metody "Public" lub "Private"

W przypadku zastosowania do zarządzanej klasy lub struktury słowa kluczowe [Public](../../cpp/public-cpp.md) i [Private](../../cpp/private-cpp.md) wskazują, czy Klasa zostanie udostępniona za pomocą metadanych zestawu. Tylko `public` lub `private` mogą być stosowane do klasy w programie skompilowanym za pomocą [/CLR](../../build/reference/clr-common-language-runtime-compilation.md).

`ref` `value` Słowa kluczowe i, jeśli są używane z [/CLR](../../build/reference/clr-common-language-runtime-compilation.md), wskazują, że Klasa jest zarządzana (zobacz [klasy i struktury](../../extensions/classes-and-structs-cpp-component-extensions.md)).

Poniższy przykład generuje C3380:

```cpp
// C3380_2.cpp
// compile with: /clr
protected ref class A {   // C3380
// try the following line instead
// ref class A {
public:
   static int i = 9;
};

int main() {
   A^ myA = gcnew A;
   System::Console::WriteLine(myA->i);
}
```
