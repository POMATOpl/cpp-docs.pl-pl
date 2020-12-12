---
description: 'Dowiedz się więcej o: błąd kompilatora C3097'
title: Błąd kompilatora C3097
ms.date: 11/04/2016
f1_keywords:
- C3097
helpviewer_keywords:
- C3097
ms.assetid: b24bd8f8-e04f-4fbb-be57-4feb9165572e
ms.openlocfilehash: aa728a7f4feecad71671dfa6fe6edc6a980b1310
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97116239"
---
# <a name="compiler-error-c3097"></a>Błąd kompilatora C3097

"Attribute": atrybut musi być objęty zakresem "Assembly:" lub "module:"

Atrybut globalny został użyty nieprawidłowo.

Aby uzyskać więcej informacji, zobacz [atrybuty zdefiniowane przez użytkownika](../../extensions/user-defined-attributes-cpp-component-extensions.md).

## <a name="example"></a>Przykład

Poniższy przykład generuje C3097.

```cpp
// C3097.cpp
// compile with: /clr /c
using namespace System;

[AttributeUsage(AttributeTargets::All, AllowMultiple = true)]
public ref class Attr : public Attribute {
public:
   Attr(int t) : m_t(t) {}
   int m_t;
};

[Attr(10)];   // C3097
[assembly:Attr(10)];   // OK

[Attr(10)]   // OK
public ref class MyClass {};
```
