---
title: Błąd kompilatora C2309
ms.date: 11/04/2016
f1_keywords:
- C2309
helpviewer_keywords:
- C2309
ms.assetid: 6303d5b5-72cf-42b8-92ce-b1eb48e80d48
ms.openlocfilehash: 9d114565b6b119711aaa773d76658cc27838f4a9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/23/2019
ms.locfileid: "62303545"
---
# <a name="compiler-error-c2309"></a>Błąd kompilatora C2309

przy obsłudze catch Oczekiwano deklaracji wyjątku ujętego w nawiasy

Procedury obsługi catch nie ma ujęty w nawiasy typu.

Poniższy przykład spowoduje wygenerowanie C2309:

```
// C2309.cpp
// compile with: /EHsc
#include <eh.h>
class C {};
int main() {
   try {
      throw "ooops!";
   }
   catch C {}   // C2309
   // try the following line instead
   // catch( C ) {}
}
```