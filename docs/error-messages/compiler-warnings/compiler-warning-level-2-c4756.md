---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 2) C4756'
title: Ostrzeżenie kompilatora (poziom 2) C4756
ms.date: 11/04/2016
f1_keywords:
- C4756
helpviewer_keywords:
- C4756
ms.assetid: 5a16df83-6b82-4619-83bd-319af4ef1d1d
ms.openlocfilehash: 3031a882feaba0d96adf588481de29431b337ad7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97173457"
---
# <a name="compiler-warning-level-2-c4756"></a>Ostrzeżenie kompilatora (poziom 2) C4756

przepełnienie w stałej arytmetycznej

Kompilator wygenerował wyjątek podczas wykonywania stałej arytmetycznej podczas kompilacji.

Poniższy przykład generuje C4756:

```cpp
// C4756.cpp
// compile with: /W2 /Od
int main()
{
   float f = 1e100+1e100;   // C4756
}
```
