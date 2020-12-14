---
description: 'Dowiedz się więcej o: błąd kompilatora C2015'
title: Błąd kompilatora C2015
ms.date: 11/04/2016
f1_keywords:
- C2015
helpviewer_keywords:
- C2015
ms.assetid: 8f40af0a-3a5a-4d6a-8ed7-125966e6bfed
ms.openlocfilehash: 0c27dbf8f7383ebd6424e9482fd1ce8cc0839a39
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97220958"
---
# <a name="compiler-error-c2015"></a>Błąd kompilatora C2015

zbyt wiele znaków w stałej

Stała znakowa zawiera więcej niż dwa znaki. Limit jest jednym znakiem dla stałych znaków standardowych i dwóch znaków dla stałych znaków długich.

Sekwencja ucieczki, taka jak \t, jest konwertowana na pojedynczy znak.

## <a name="examples"></a>Przykłady

Poniższy przykład generuje C2015:

```cpp
// C2015.cpp
// compile with: /c

char test1 = 'error';   // C2015
char test2 = 'e';   // OK
```

C2015 może również wystąpić w przypadku korzystania z rozszerzenia Microsoft, stałe znakowe konwertowane na liczby całkowite.  Poniższy przykład generuje C2015:

```cpp
// C2015b.cpp
#include <stdio.h>

int main()
{
    int a = 'abcde';   // C2015

    int b = 'a';   // 'a' = ascii 0x61
    printf_s("%x\n", b);
}
```
