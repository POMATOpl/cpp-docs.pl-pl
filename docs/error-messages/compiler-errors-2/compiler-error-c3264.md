---
title: Błąd kompilatora C3264
ms.date: 11/04/2016
f1_keywords:
- C3264
helpviewer_keywords:
- C3264
ms.assetid: 94ece687-2364-4f7a-8ebb-7afd3ae9d63d
ms.openlocfilehash: 2f5a58335a36affc73deb490c9423284852ecbab
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/23/2019
ms.locfileid: "62366254"
---
# <a name="compiler-error-c3264"></a>Błąd kompilatora C3264

"class": konstruktor klasy nie może posiadać typu zwracanego

Konstruktory klasy nie może mieć zwracanych typów.

Poniższy przykład spowoduje wygenerowanie C3264:

```
// C3264_2.cpp
// compile with: /clr

ref class X {
   public:
      static int X()   { // C3264
      }

      /* use the code below to resolve the error
      static X() {
      }
      */
};
int main() {
}
```
