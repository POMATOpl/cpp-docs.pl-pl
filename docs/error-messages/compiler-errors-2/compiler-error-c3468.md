---
description: 'Dowiedz się więcej o: błąd kompilatora C3468'
title: Błąd kompilatora C3468
ms.date: 11/04/2016
f1_keywords:
- C3468
helpviewer_keywords:
- C3468
ms.assetid: cfd320db-2f6e-4e0d-ba02-e79ece87e1e0
ms.openlocfilehash: 7e6d58e012baa0163f33867069e7250da61177b2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97315741"
---
# <a name="compiler-error-c3468"></a>Błąd kompilatora C3468

"Type": można tylko przesłać dalej typ do zestawu:

element " `file` " nie jest zestawem

Można przesłać dalej tylko typy w zestawie.

Aby uzyskać więcej informacji, zobacz [przekazywanie dalej typu (C++/CLI)](../../extensions/type-forwarding-cpp-cli.md).

## <a name="examples"></a>Przykłady

Poniższy przykład tworzy moduł.

```cpp
// C3468.cpp
// compile with: /LN /clr
public ref class R {};
```

Poniższy przykład generuje C3468.

```cpp
// C3468_b.cpp
// compile with: /clr /c
#using "C3468.netmodule"
[ assembly:TypeForwardedTo(R::typeid) ];   // C3468
```
