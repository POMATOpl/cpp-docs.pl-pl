---
description: 'Dowiedz się więcej o: błąd kompilatora C3185'
title: Błąd kompilatora C3185
ms.date: 11/04/2016
f1_keywords:
- C3185
helpviewer_keywords:
- C3185
ms.assetid: 5bf96279-043c-4981-9d02-b4550071b192
ms.openlocfilehash: 7dbcf11aa7c88d883aeccc8325832849f8b7a238
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97242018"
---
# <a name="compiler-error-c3185"></a>Błąd kompilatora C3185

element "typeid" jest używany w typie zarządzanym lub typu WinRT "Type", Użyj zamiast niego operatora "operator"

Nie można zastosować operatora [typeid](../../cpp/typeid-operator.md) do typu zarządzanego lub WinRT; Użyj zamiast tego elementu [typeid](../../extensions/typeid-cpp-component-extensions.md) .

Poniższy przykład generuje C3185 i pokazuje, jak to naprawić:

```cpp
// C3185a.cpp
// compile with: /clr
ref class Base {};
ref class Derived : public Base {};

int main() {
   Derived ^ pd = gcnew Derived;
   Base ^pb = pd;
   const type_info & t1 = typeid(pb);   // C3185
   System::Type ^ MyType = Base::typeid;   // OK
};
```
