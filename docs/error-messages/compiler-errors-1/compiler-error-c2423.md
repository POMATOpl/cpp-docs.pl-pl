---
title: Błąd kompilatora C2423
ms.date: 11/04/2016
f1_keywords:
- C2423
helpviewer_keywords:
- C2423
ms.assetid: 8797fb8b-b58b-4add-b6e6-2a9a3cd9084d
ms.openlocfilehash: 47598ac08c0f8b6b41d88daf9e1eb9f0ca00131b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/23/2019
ms.locfileid: "62402888"
---
# <a name="compiler-error-c2423"></a>Błąd kompilatora C2423

"numer": niedozwolona Skala

Wbudowany kod asemblera używa wielu innych niż 1, 2, 4 lub 8 skalowanie do rejestru.

Poniższy przykład spowoduje wygenerowanie C2423:

```
// C2423.cpp
// processor: x86
int main() {
   _asm {
      lea EAX, [EAX*3]   // C2423
      lea EAX, [EAX+EAX*2]   // OK
   }
}
```