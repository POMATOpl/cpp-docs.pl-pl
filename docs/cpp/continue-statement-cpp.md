---
description: 'Dowiedz się więcej na temat: Continue — instrukcja (C++)'
title: continue — instrukcja (C++)
ms.date: 11/04/2016
f1_keywords:
- continue_cpp
helpviewer_keywords:
- continue keyword [C++]
ms.assetid: 3c94ee57-f732-4c1d-8537-d0ce5382bfd4
ms.openlocfilehash: 6899e5cd249ab5a7a3b786e4b82c9890c08a7183
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97344643"
---
# <a name="continue-statement-c"></a>continue — instrukcja (C++)

Wymusza przeniesienie kontroli do wyrażenia sterującego najmniejszej otaczającej pętli [Zrób](../cpp/do-while-statement-cpp.md), [for](../cpp/for-statement-cpp.md)lub [while](../cpp/while-statement-cpp.md) .

## <a name="syntax"></a>Składnia

```
continue;
```

## <a name="remarks"></a>Uwagi

Wszystkie pozostałe instrukcje w bieżącej iteracji nie są wykonywane. Następna iteracja pętli jest określana w następujący sposób:

- W **`do`** pętli lub **`while`** , następna iteracja jest uruchamiana przez ponowną ocenę wyrażenia sterującego **`do`** instrukcji or **`while`** .

- W **`for`** pętli (przy użyciu składni `for( <init-expr> ; <cond-expr> ; <loop-expr> )` ) `<loop-expr>` klauzula jest wykonywana. Następnie `<cond-expr>` klauzula jest ponownie Szacowana i, w zależności od wyniku, pętla lub zostanie zakończona.

Poniższy przykład pokazuje, jak **`continue`** można użyć instrukcji w celu obejścia sekcji kodu i rozpoczęcia następnej iteracji pętli.

## <a name="example"></a>Przykład

```cpp
// continue_statement.cpp
#include <stdio.h>
int main()
{
    int i = 0;
    do
    {
        i++;
        printf_s("before the continue\n");
        continue;
        printf("after the continue, should never print\n");
     } while (i < 3);

     printf_s("after the do loop\n");
}
```

```Output
before the continue
before the continue
before the continue
after the do loop
```

## <a name="see-also"></a>Zobacz także

[Instrukcje skoku](../cpp/jump-statements-cpp.md)<br/>
[Słowa kluczowe](../cpp/keywords-cpp.md)
