---
description: 'Dowiedz się więcej o: błąd kompilatora C3461'
title: Błąd kompilatora C3461
ms.date: 11/04/2016
f1_keywords:
- C3461
helpviewer_keywords:
- C3461
ms.assetid: bd66833a-545d-445a-bdfe-dee771a450a4
ms.openlocfilehash: 6158e0d6d38290a1925beba89fe77cba8f01c87b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97113496"
---
# <a name="compiler-error-c3461"></a>Błąd kompilatora C3461

"Type": tylko typ zarządzany może być przekazywany

Przekazywanie typu może wystąpić tylko w przypadku typów CLR.  Aby uzyskać więcej informacji [, zobacz klasy i struktury](../../extensions/classes-and-structs-cpp-component-extensions.md) .

Aby uzyskać więcej informacji, zobacz [przekazywanie dalej typu (C++/CLI)](../../extensions/type-forwarding-cpp-cli.md).

## <a name="examples"></a>Przykłady

Poniższy przykład tworzy składnik.

```cpp
// C3461.cpp
// compile with: /clr /LD
public ref class R {};
```

Poniższy przykład generuje C3461.

```cpp
// C3461b.cpp
// compile with: /clr /c
#using "C3461.dll"
class N {};
[assembly:TypeForwardedTo(N::typeid)];   // C3461
[assembly:TypeForwardedTo(R::typeid)];   // OK
```
