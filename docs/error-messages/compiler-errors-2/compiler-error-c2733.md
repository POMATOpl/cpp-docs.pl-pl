---
description: 'Dowiedz się więcej o: błąd kompilatora C2733'
title: Błąd kompilatora C2733
ms.date: 11/04/2016
f1_keywords:
- C2733
helpviewer_keywords:
- C2733
ms.assetid: 67f83561-c633-407c-a2ee-f9fd16e165bf
ms.openlocfilehash: f957be13b8c1de1ee3ada98ffd42f0d89fc7755c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97123204"
---
# <a name="compiler-error-c2733"></a>Błąd kompilatora C2733

drugie powiązanie C przeciążonej funkcji "Function" jest niedozwolone

Z powiązaniem C jest zadeklarowana więcej niż jedna przeciążona funkcja. W przypadku korzystania z połączenia C tylko jedna forma określonej funkcji może być zewnętrzna. Ponieważ przeciążone funkcje mają tę samą niedekoracyjną nazwę, nie mogą być używane z programami języka C.

Poniższy przykład generuje C2733:

```cpp
// C2733.cpp
extern "C" {
   void F1(int);
}

extern "C" {
   void F1();   // C2733
   // try the following line instead
   // void F2();
}
```
