---
description: 'Dowiedz się więcej na temat: błąd krytyczny C1094'
title: Błąd krytyczny C1094
ms.date: 11/04/2016
f1_keywords:
- C1094
helpviewer_keywords:
- C1094
ms.assetid: 9e1193b2-cb95-44f9-bf6f-019e0d41dd97
ms.openlocfilehash: af83c6fa80a6e1b115146ad05513539fea7d348c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97145096"
---
# <a name="fatal-error-c1094"></a>Błąd krytyczny C1094

"-Zmval1": opcja wiersza polecenia jest niespójna z wartością używaną do kompilowania prekompilowanego nagłówka ("-Zmval2")

Wartość, która jest przenoszona do [/YC](../../build/reference/yc-create-precompiled-header-file.md) musi być tą samą wartością, która jest przenoszona do [/Yu](../../build/reference/yu-use-precompiled-header-file.md) (wartości **/zm** muszą być takie same we wszystkich kompilacjach, które używają lub tworzą ten sam prekompilowany plik nagłówkowy).

Poniższy przykład generuje C1094:

```
// C1094.h
int func1();
```

A następnie

```cpp
// C1094.cpp
// compile with: /Yc"C1094.h" /Zm200
int u;
int main() {
   int sd = 32;
}
#include "C1094.h"
```

A następnie

```cpp
// C1094b.cpp
// compile with: /Yu"C1094.h" /Zm300 /c
#include "C1094.h"   // C1094 compile with /Zm200
void Test() {}
```
