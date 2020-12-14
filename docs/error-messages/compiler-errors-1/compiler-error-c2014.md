---
description: 'Dowiedz się więcej o: błąd kompilatora C2014'
title: Błąd kompilatora C2014
ms.date: 11/04/2016
f1_keywords:
- C2014
helpviewer_keywords:
- C2014
ms.assetid: 231d8e9c-48c0-4027-99a3-245d186275ec
ms.openlocfilehash: 2f8de1d2b9ea8ef680826cfbfc189dbe2617c9f6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97220984"
---
# <a name="compiler-error-c2014"></a>Błąd kompilatora C2014

polecenie preprocesora musi zaczynać się od pierwszego niebiałego znaku

`#`Znak dyrektywy preprocesora musi być pierwszym znakiem w wierszu, który nie jest znakiem odstępu.

Poniższy przykład generuje C2014:

```cpp
// C2014.cpp
int k; #include <stdio.h>   // C2014
```

Możliwe rozwiązanie:

```cpp
// C2014b.cpp
// compile with: /c
int k;
#include <stdio.h>
```
