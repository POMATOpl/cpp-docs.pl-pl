---
description: 'Dowiedz się więcej o: błąd kompilatora C2012'
title: Błąd kompilatora C2012
ms.date: 11/04/2016
f1_keywords:
- C2012
helpviewer_keywords:
- C2012
ms.assetid: 9f0d8162-c0b3-4234-a41f-836fdb75c84e
ms.openlocfilehash: 82f2a5660ec3920c9ff3db57c6ed0b70516c4531
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97221010"
---
# <a name="compiler-error-c2012"></a>Błąd kompilatora C2012

Brak nazwy po "<"

`#include`Dyrektywa nie ma wymaganej nazwy pliku.

Poniższy przykład generuje C2012:

```cpp
// C2012.cpp
#include <   // C2012 include the filename to resolve
```

Możliwe rozwiązanie:

```cpp
// C2012b.cpp
// compile with: /c
#include <stdio.h>
```
