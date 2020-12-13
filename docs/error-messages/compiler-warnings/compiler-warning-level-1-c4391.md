---
description: 'Dowiedz się więcej o: Ostrzeżenie kompilatora (poziom 1) C4391'
title: Ostrzeżenie kompilatora (poziom 1) C4391
ms.date: 11/04/2016
f1_keywords:
- C4391
helpviewer_keywords:
- C4391
ms.assetid: 95c6182c-fae9-4174-8f7b-98aa352e68ca
ms.openlocfilehash: 89c3babcf78dd47188cb03afa629a5aeda923fc7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97339916"
---
# <a name="compiler-warning-level-1-c4391"></a>Ostrzeżenie kompilatora (poziom 1) C4391

"Signature": nieprawidłowy typ zwracany dla wewnętrznej funkcji, oczekiwano "Type"

Deklaracja funkcji dla wewnętrznego kompilatora ma nieprawidłowy zwracany typ. Obraz z wynikiem może nie działać poprawnie.

Aby usunąć to ostrzeżenie, Popraw deklarację lub Usuń deklarację i po prostu #include odpowiedni plik nagłówkowy.

Poniższy przykład generuje C4391:

```cpp
// C4391.cpp
// compile with: /W1
// processor: x86
// uncomment the following line and delete the line that
// generated the warning to resolve
// #include "xmmintrin.h"

#ifdef  __cplusplus
extern "C" {
#endif

extern void _mm_load_ss(float *p);   // C4391

#ifdef  __cplusplus
}
#endif

int main()
{
}
```
