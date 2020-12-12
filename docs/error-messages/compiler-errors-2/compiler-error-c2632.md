---
description: 'Dowiedz się więcej o: błąd kompilatora C2632'
title: Błąd kompilatora C2632
ms.date: 11/04/2016
f1_keywords:
- C2632
helpviewer_keywords:
- C2632
ms.assetid: b15a6b1b-42d2-4e1b-8660-e6bfde61052d
ms.openlocfilehash: b6f1091b512d3a01efa933c998bde3d0885bbff1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97123516"
---
# <a name="compiler-error-c2632"></a>Błąd kompilatora C2632

element "type1", po którym następuje wyrażenie "type2", jest niedozwolony

Ten błąd może być spowodowany brakiem kodu między dwoma specyfikatorami typu.

Poniższy przykład generuje C2632:

```cpp
// C2632.cpp
int float i;   // C2632
```

Ten błąd może być również wygenerowany w wyniku działania kompilatora, który został wykonany dla programu Visual Studio .NET 2003. **`bool`** jest teraz prawidłowym typem. W poprzednich wersjach **`bool`** była elementem TypeDef i można utworzyć identyfikatory o tej nazwie.

Poniższy przykład generuje C2632:

```cpp
// C2632_2.cpp
// compile with: /LD
void f(int bool);   // C2632
```

Aby rozwiązać ten problem, aby kod był prawidłowy w wersjach programu Visual Studio .NET 2003 i Visual Studio .NET Visual C++, Zmień nazwę identyfikatora.
