---
description: 'Dowiedz się więcej o: błąd kompilatora C2428'
title: Błąd kompilatora C2428
ms.date: 11/04/2016
f1_keywords:
- C2428
helpviewer_keywords:
- C2428
ms.assetid: 74aa5714-e930-4f9e-9061-68ccce7f0d38
ms.openlocfilehash: a91819591251e1c291ef8a3291525c0493af20ad
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97190149"
---
# <a name="compiler-error-c2428"></a>Błąd kompilatora C2428

"Operation": niedozwolone na operandzie typu "bool"

Nie można zastosować operatora zmniejszania do obiektów typu **`bool`** .

Poniższy przykład generuje C2428:

```cpp
// C2428.cpp
void g(bool fFlag) {
   --fFlag;   // C2428
   fFlag--;   // C2428
}
```
