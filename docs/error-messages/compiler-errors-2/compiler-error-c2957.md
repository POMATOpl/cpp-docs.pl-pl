---
title: Błąd kompilatora C2957
ms.date: 11/04/2016
f1_keywords:
- C2957
helpviewer_keywords:
- C2957
ms.assetid: 9cb4526f-4af8-47e9-b786-56192627ca72
ms.openlocfilehash: 51745b60d89c28280c8c48cdbba3762d92529073
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/23/2019
ms.locfileid: "62300755"
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