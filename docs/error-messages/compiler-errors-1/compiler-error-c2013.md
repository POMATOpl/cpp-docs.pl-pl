---
description: 'Dowiedz się więcej o: błąd kompilatora C2013'
title: Błąd kompilatora C2013
ms.date: 11/04/2016
f1_keywords:
- C2013
helpviewer_keywords:
- C2013
ms.assetid: 6b5c955c-53da-48ee-8533-64ef5b905173
ms.openlocfilehash: 2f883c24be5e02c58553ca6f7abe4f588ae8a2da
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97220971"
---
# <a name="compiler-error-c2013"></a>Błąd kompilatora C2013

Brak ">"

Dyrektywa nie ma `#include` zamykającego nawiasu ostrego. Aby rozwiązać ten problem, Dodaj nawias zamykający.

Poniższy przykład generuje C2013:

```cpp
// C2013.cpp
#include <stdio.h    // C2013
```

Możliwe rozwiązanie:

```cpp
// C2013b.cpp
// compile with: /c
#include <stdio.h>
```
