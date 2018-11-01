---
title: Błąd kompilatora C2957
ms.date: 11/04/2016
f1_keywords:
- C2957
helpviewer_keywords:
- C2957
ms.assetid: 9cb4526f-4af8-47e9-b786-56192627ca72
ms.openlocfilehash: 51745b60d89c28280c8c48cdbba3762d92529073
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/31/2018
ms.locfileid: "50600505"
---
# <a name="compiler-error-c2957"></a>Błąd kompilatora C2957

"delim": Nieprawidłowy lewy ogranicznik: oczekiwano "<"

Klasa generyczna został niewłaściwie sformatowany.

Poniższy przykład spowoduje wygenerowanie C2957:

```
// C2957.cpp
// compile with: /clr /LD
generic << class T>   // C2957
// try the following line instead
// generic < class T>
gc class C {};
```