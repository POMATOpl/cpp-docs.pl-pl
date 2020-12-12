---
description: 'Dowiedz się więcej o: błąd kompilatora C2006'
title: Błąd kompilatora C2006
ms.date: 11/04/2016
f1_keywords:
- C2006
helpviewer_keywords:
- C2006
ms.assetid: caaed6f7-ceb9-4742-8820-d66657c0b04d
ms.openlocfilehash: 5747f5417db60bd3c1f7bc1420c257552a9b42c7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97298516"
---
# <a name="compiler-error-c2006"></a>Błąd kompilatora C2006

"dyrektywa" oczekuje nazwy pliku, znaleziono "token"

Dyrektywy takie jak [#include](../../preprocessor/hash-include-directive-c-cpp.md) lub [#import](../../preprocessor/hash-import-directive-cpp.md) wymagają pliku filename. Aby rozwiązać ten problem, upewnij się, że *token* jest prawidłową nazwą pliku. Należy również umieścić nazwę pliku w podwójnych cudzysłowach lub nawiasach kątowych.

Poniższy przykład generuje C2006:

```cpp
// C2006.cpp
#include stdio.h   // C2006
```

Możliwe rozwiązanie:

```cpp
// C2006b.cpp
// compile with: /c
#include <stdio.h>
```
