---
title: Błąd kompilatora C2505
ms.date: 11/04/2016
f1_keywords:
- C2505
helpviewer_keywords:
- C2505
ms.assetid: b19f5c53-399d-425e-90db-fe3ca9b40858
ms.openlocfilehash: bf5ffb9b6bad3db1d264941a6aefa391be521c98
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/23/2019
ms.locfileid: "62165045"
---
# <a name="compiler-error-c2505"></a>Błąd kompilatora C2505

'symbol': "__declspec(modifer)" będzie stosowany tylko do deklaracji lub definicji obiektów globalnych albo statycznych składowych danych

A `__declspec` modyfikatory, które mają być używane tylko w zakresie globalnym był używany w funkcji.

Aby uzyskać więcej informacji, zobacz [appdomain](../../cpp/appdomain.md) i [procesu](../../cpp/process.md).

Poniższy przykład spowoduje wygenerowanie C2505:

```
// C2505.cpp
// compile with: /clr

// OK
__declspec(process) int ii;
__declspec(appdomain) int jj;

int main() {
   __declspec(process) int i;   // C2505
   __declspec(appdomain) int j;   // C2505
}
```