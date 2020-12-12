---
description: 'Dowiedz się więcej o: błąd kompilatora C2563'
title: Błąd kompilatora C2563
ms.date: 11/04/2016
f1_keywords:
- C2563
helpviewer_keywords:
- C2563
ms.assetid: 54abba68-6458-4ca5-894d-3babdb7b3552
ms.openlocfilehash: 2243e0820b2e69d6bc05351fdba4600188a3ac08
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97209155"
---
# <a name="compiler-error-c2563"></a>Błąd kompilatora C2563

niezgodność w formalnej liście parametrów

Formalna lista parametrów funkcji (lub wskaźnika do funkcji) nie jest zgodna z innymi funkcjami (lub wskaźnikiem do funkcji składowej). W związku z tym nie można wykonać przypisania funkcji ani wskaźników.

Poniższy przykład generuje C2563:

```cpp
// C2563.cpp
void func( int );
void func( int, int );
int main() {
   void *fp();
   fp = func;   // C2563
}
```
