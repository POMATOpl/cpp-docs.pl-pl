---
title: Błąd kompilatora C3075
ms.date: 11/04/2016
f1_keywords:
- C3075
helpviewer_keywords:
- C3075
ms.assetid: f431daa9-e0fa-48f0-a5c3-f99be96b55e3
ms.openlocfilehash: 345cdd17b9da0be8f8d6e9f7b5f48624ade412bd
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/03/2019
ms.locfileid: "74761585"
---
# <a name="compiler-error-c3075"></a>Błąd kompilatora C3075

"wystąpienie": nie można osadzić wystąpienia typu referencyjnego "Type" w typie wartości

Typ wartości nie może zawierać wystąpienia typu referencyjnego.

Aby uzyskać więcej informacji, zobacz [ C++ semantyka stosu dla typów referencyjnych](../../dotnet/cpp-stack-semantics-for-reference-types.md).

## <a name="example"></a>Przykład

Poniższy przykład generuje C3075.

```cpp
// C3075.cpp
// compile with: /clr /c
ref struct U {};
value struct X {
   U y;   // C3075
};

ref struct Y {
   U y;   // OK
};
```
