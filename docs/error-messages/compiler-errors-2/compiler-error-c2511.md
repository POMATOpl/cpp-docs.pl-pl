---
description: 'Dowiedz się więcej o: błąd kompilatora C2511'
title: Błąd kompilatora C2511
ms.date: 11/04/2016
f1_keywords:
- C2511
helpviewer_keywords:
- C2511
ms.assetid: df999efe-fe2b-418b-bb55-4af6a0592631
ms.openlocfilehash: 846173cc887fd09b564d18e063820bc0e0d5b184
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97212925"
---
# <a name="compiler-error-c2511"></a>Błąd kompilatora C2511

"Identyfikator": przeciążona Funkcja składowa nie została znaleziona w "Class"

Żadna wersja funkcji nie jest zadeklarowana z określonymi parametrami.  Możliwe przyczyny:

1. Do funkcji przeszedł nieprawidłowe parametry.

1. Parametry zostały przesłane w złej kolejności.

1. Niepoprawna pisownia nazw parametrów.

Poniższy przykład generuje C2511:

```cpp
// C2511.cpp
// compile with: /c
class C {
   int c_2;
   int Func(char *, char *);
};

int C::Func(char *, char *, int i) {   // C2511
// try the following line instead
// int C::Func(char *, char *) {
   return 0;
}
```
