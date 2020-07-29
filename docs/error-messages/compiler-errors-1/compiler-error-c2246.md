---
title: Błąd kompilatora C2246
ms.date: 11/04/2016
f1_keywords:
- C2246
helpviewer_keywords:
- C2246
ms.assetid: 4f3e4f83-21f3-4256-af96-43e0bb060311
ms.openlocfilehash: c7dac0abb7d65d3f26522ea1a04577643b7b9eca
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/27/2020
ms.locfileid: "87212829"
---
# <a name="compiler-error-c2246"></a>Błąd kompilatora C2246

"Identyfikator": niedozwolony statyczny element członkowski danych w klasie zdefiniowanej lokalnie

Jest zadeklarowany element członkowski klasy, struktury lub Unii z zakresem lokalnym **`static`** .

Poniższy przykład generuje C2246:

```cpp
// C2246.cpp
// compile with: /c
void func( void ) {
   class A { static int i; };   // C2246  i is local to func
   static int j;   // OK
};
```
