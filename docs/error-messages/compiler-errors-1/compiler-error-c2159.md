---
title: Błąd kompilatora C2159
ms.date: 11/04/2016
f1_keywords:
- C2159
helpviewer_keywords:
- C2159
ms.assetid: 925a2cbd-43c9-45ee-a373-84004350b380
ms.openlocfilehash: fd845fffe9778e51af7db77144607233ed9ddefd
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/31/2018
ms.locfileid: "50575113"
---
# <a name="compiler-error-c2159"></a>Błąd kompilatora C2159

więcej niż jedną klasę magazynu określony

Deklaracja zawiera więcej niż jedną klasę magazynu.

Poniższy przykład spowoduje wygenerowanie C2159:

```
// C2159.cpp
// compile with: /c
static int i;   // OK
extern static int i;   // C2159
```