---
title: Błąd kompilatora C2053
ms.date: 11/04/2016
f1_keywords:
- C2053
helpviewer_keywords:
- C2053
ms.assetid: 13324c85-13a8-4996-bd42-a31bfe7ff80f
ms.openlocfilehash: be5517ce77872fe395a52c5b1e0070612e205a3d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/31/2018
ms.locfileid: "50571226"
---
# <a name="compiler-error-c2053"></a>Błąd kompilatora C2053

'Identyfikator': niezgodność szerokości ciągu

Niezgodny typ przydzielono szerokiego ciągu.

Poniższy przykład spowoduje wygenerowanie C2053:

```
// C2053.c
int main() {
   char array[] = L"Rika";   // C2053
}
```