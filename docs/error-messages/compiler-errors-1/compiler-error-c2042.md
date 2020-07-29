---
title: Błąd kompilatora C2042
ms.date: 11/04/2016
f1_keywords:
- C2042
helpviewer_keywords:
- C2042
ms.assetid: e111788f-41ce-405a-9824-a4c1c26059e6
ms.openlocfilehash: 9851d952c4a07eacd223394f10183d0ec9c369bc
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/27/2020
ms.locfileid: "87212894"
---
# <a name="compiler-error-c2042"></a>Błąd kompilatora C2042

podpisane i niepodpisane słowa kluczowe wzajemnie się wykluczają

Słowa kluczowe **`signed`** i **`unsigned`** są używane w pojedynczej deklaracji.

Poniższy przykład generuje C2042:

```cpp
// C2042.cpp
unsigned signed int i;   // C2042
```

Możliwe rozwiązanie:

```cpp
// C2042b.cpp
// compile with: /c
unsigned int i;
signed int ii;
```
