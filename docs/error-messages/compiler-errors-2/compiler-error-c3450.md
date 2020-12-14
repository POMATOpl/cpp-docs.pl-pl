---
description: 'Dowiedz się więcej o: błąd kompilatora C3450'
title: Błąd kompilatora C3450
ms.date: 11/04/2016
f1_keywords:
- C3450
helpviewer_keywords:
- C3450
ms.assetid: 78892cf7-0b82-4589-90d0-e06666247003
ms.openlocfilehash: e56382a3f71b59fee42b6a545318cf3846e1a1f7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97316053"
---
# <a name="compiler-error-c3450"></a>Błąd kompilatora C3450

"Type": nie jest atrybutem; nie można określić [System:: AttributeUsageAttribute] ani [Windows:: Foundation:: Metadata:: AttributeUsageAttribute]

Zdefiniowany przez użytkownika atrybut zarządzany musi dziedziczyć po elemencie <xref:System.ComponentModel.AttributeCollection.%23ctor%2A> . Atrybut środowisko wykonawcze systemu Windows musi być zdefiniowany w `Windows::Foundation::Metadata` przestrzeni nazw.

Aby uzyskać więcej informacji, zobacz [atrybuty zdefiniowane przez użytkownika](../../extensions/user-defined-attributes-cpp-component-extensions.md).

## <a name="example"></a>Przykład

Poniższy przykład generuje C3450 i pokazuje, jak rozwiązać ten problem.

```cpp
// C3450.cpp
// compile with: /clr
// C3450 expected
using namespace System;
using namespace System::Security;
using namespace System::Security::Permissions;

public ref class MyClass {};

class MyClass2 {};

[attribute(AttributeTargets::All)]
ref struct AtClass {
   AtClass(Type ^) {}
};

[attribute(AttributeTargets::All)]
ref struct AtClass2 {
   AtClass2() {}
};

// Apply the AtClass and AtClass2 attributes to class B
[AtClass(MyClass::typeid), AtClass2]
[AttributeUsage(AttributeTargets::All)]
// Delete the following line to resolve.
ref class B {};
// Uncomment the following line to resolve.
// ref class B : Attribute {};
```
