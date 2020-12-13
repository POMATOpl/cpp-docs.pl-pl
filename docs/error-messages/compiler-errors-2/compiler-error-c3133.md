---
description: 'Dowiedz się więcej o: błąd kompilatora C3133'
title: Błąd kompilatora C3133
ms.date: 11/04/2016
f1_keywords:
- C3133
helpviewer_keywords:
- C3133
ms.assetid: 4a709405-b67b-4061-8a2a-19fa5fb34a2a
ms.openlocfilehash: 3559e5864ea5f8d5e690a77899d6314ee2b65519
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97177383"
---
# <a name="compiler-error-c3133"></a>Błąd kompilatora C3133

Nie można zastosować atrybutów do typu VarArgs języka C++

Atrybut został zastosowany nieprawidłowo. Nie można zastosować atrybutów do wielokropka reprezentującego argumenty zmienne.

Aby uzyskać więcej informacji, zobacz [atrybuty zdefiniowane przez użytkownika](../../extensions/user-defined-attributes-cpp-component-extensions.md).

## <a name="example"></a>Przykład

Poniższy przykład generuje C3133.

```cpp
// C3133.cpp
// compile with: /clr /c
ref struct MyAttr: System::Attribute {};
void Func([MyAttr]...);   // C3133
void Func2([MyAttr] int i);   // OK
```
