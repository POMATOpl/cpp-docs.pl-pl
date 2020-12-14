---
description: 'Dowiedz się więcej o: błąd kompilatora C2001'
title: Błąd kompilatora C2001
ms.date: 11/04/2016
f1_keywords:
- C2001
helpviewer_keywords:
- C2001
ms.assetid: 0c3a7821-d8e5-4398-ab5a-4116d46e8dda
ms.openlocfilehash: 81c033288ae673e95bc3454e2754d371f84225e5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97298633"
---
# <a name="compiler-error-c2001"></a>Błąd kompilatora C2001

stała nowego wiersza

Stała ciągu nie może być kontynuowana w drugim wierszu, chyba że wykonasz następujące czynności:

- Zakończ pierwszy wiersz za pomocą ukośnika odwrotnego.

- Zamknij ciąg w pierwszym wierszu ze znakiem podwójnego cudzysłowu i Otwórz ciąg w następnym wierszu z innym znakiem podwójnego cudzysłowu.

Zakończenie pierwszego wiersza za pomocą \n nie jest wystarczające.

## <a name="examples"></a>Przykłady

Poniższy przykład generuje C2001:

```cpp
// C2001.cpp
// C2001 expected
#include <stdio.h>

int main()
{
    printf_s("Hello,
             world");
    printf_s("Hello,\n
             world");
}
```

Spacje na początku następnego wiersza po znaku kontynuacji wiersza są uwzględniane w stałej ciągu. Żaden z przykładów pokazanych powyżej nie osadzi znaku nowego wiersza do stałej ciągu. Możesz osadzić znak nowego wiersza, jak pokazano poniżej:

```cpp
// C2001b.cpp
#include <stdio.h>

int main()
{
    printf_s("Hello,\n\
             world");

    printf_s("Hello,\
             \nworld");

    printf_s("Hello,\n"
             "world");

    printf_s("Hello,"
             "\nworld");

    printf_s("Hello,"
             " world");

    printf_s("Hello,\
             world");
}
```
