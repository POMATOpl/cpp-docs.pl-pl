---
title: Błąd kompilatora C3466
ms.date: 11/04/2016
f1_keywords:
- C3466
helpviewer_keywords:
- C3466
ms.assetid: 69a877d9-a749-474b-bfc3-8d3fd53ba8fd
ms.openlocfilehash: 689a0ca837cf305840d6f080e615527f01879225
ms.sourcegitcommit: 72161bcd21d1ad9cc3f12261aa84a5b026884afa
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/17/2020
ms.locfileid: "90742843"
---
# <a name="compiler-error-c3466"></a>Błąd kompilatora C3466

"Type": specjalizacji klasy generycznej nie można przesłać dalej

Nie można użyć przesyłania dalej typu dla specjalizacji klasy generycznej.

Aby uzyskać więcej informacji, zobacz [przekazywanie dalej typu (C++/CLI)](../../extensions/type-forwarding-cpp-cli.md).

## <a name="examples"></a>Przykłady

Poniższy przykład tworzy składnik.

```cpp
// C3466.cpp
// compile with: /clr /LD
generic<typename T>
public ref class GR {};

public ref class GR2 {};
```

Poniższy przykład generuje C3466.

```cpp
// C3466_b.cpp
// compile with: /clr /c
#using "C3466.dll"
[assembly:TypeForwardedTo(GR<int>::typeid)];   // C3466
[assembly:TypeForwardedTo(GR2::typeid)];   // OK
```
