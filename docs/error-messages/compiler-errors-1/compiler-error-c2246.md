---
description: 'Dowiedz się więcej o: błąd kompilatora C2246'
title: Błąd kompilatora C2246
ms.date: 11/04/2016
f1_keywords:
- C2246
helpviewer_keywords:
- C2246
ms.assetid: 4f3e4f83-21f3-4256-af96-43e0bb060311
ms.openlocfilehash: 1868389c98dd864e7d92bf33d57dbe96b831f3e0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97302207"
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
