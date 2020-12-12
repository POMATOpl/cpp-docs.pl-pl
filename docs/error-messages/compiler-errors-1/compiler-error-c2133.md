---
description: 'Dowiedz się więcej o: błąd kompilatora C2133'
title: Błąd kompilatora C2133
ms.date: 11/04/2016
f1_keywords:
- C2133
helpviewer_keywords:
- C2133
ms.assetid: 8942f9e8-9818-468f-97db-09dbd124fcae
ms.openlocfilehash: d98cb3bd8df5543ecf0426a146157300f67dd91b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97323132"
---
# <a name="compiler-error-c2133"></a>Błąd kompilatora C2133

"Identyfikator": nieznany rozmiar

Tablica bez rozmiaru jest zadeklarowana jako element członkowski klasy, struktury, Unii lub wyliczenia. Opcja/za (ANSI C) nie zezwala na tablice elementów członkowskich bez rozmiaru.

Poniższy przykład generuje C2133:

```cpp
// C2133.cpp
// compile with: /Za
struct X {
   int a[0];   // C2133 unsized array
};
```

Możliwe rozwiązanie:

```cpp
// C2133b.cpp
// compile with: /c
struct X {
   int a[0];   // no /Za
};
```
