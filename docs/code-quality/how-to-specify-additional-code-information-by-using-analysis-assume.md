---
description: Dowiedz się więcej na temat sposobu określania dodatkowych informacji o kodzie przy użyciu _Analysis_assume_.
title: Użyj _Analysis_assume_ na potrzeby wskazówek dotyczących analizy kodu
ms.date: 12/16/2020
ms.topic: conceptual
f1_keywords:
- _Analysis_assume_
helpviewer_keywords:
- _Analysis_assume_
ms.openlocfilehash: f4244a896d4334cb6c5e857e63b39be0cd53b08b
ms.sourcegitcommit: 387ce22a3b0137f99cbb856a772b5a910c9eba99
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/17/2020
ms.locfileid: "97645127"
---
# <a name="how-to-specify-additional-code-information-by-using-_analysis_assume_"></a>Jak określić dodatkowe informacje o kodzie za pomocą `_Analysis_assume_`

Możesz dostarczyć wskazówki do narzędzia analizy kodu dla kodu C/C++, które ułatwią proces analizy i zmniejszają ostrzeżenia. Aby podać dodatkowe informacje, użyj następującego makra funkcji:

`_Analysis_assume( expr )`

*`expr`* — Dowolne wyrażenie, które ma zostać obliczone na wartość true.

Narzędzie do analizy kodu zakłada, że warunek reprezentowany przez wyrażenie *`expr`* ma wartość true w punkcie, w którym znajduje się funkcja. I, pozostaje ona prawdziwa do momentu zmiany *`expr`* , na przykład przez przypisanie do zmiennej.

> [!NOTE]
> `_Analysis_assume_` nie ma wpływu na optymalizację kodu. Poza narzędzia do analizy kodu, `_Analysis_assume_` jest definiowana jako No-op.

## <a name="example"></a>Przykład

Poniższy kod używa `_Analysis_assume_` do korygowania ostrzeżenia analizy kodu [C6388](../code-quality/c6388.md):

```cpp
#include <windows.h>
#include <codeanalysis\sourceannotations.h>

using namespace vc_attributes;

//requires pc to be null
void f([Pre(Null=Yes)] char* pc);

// calls free and sets ch to null
void FreeAndNull(char** ch);

void test()
{
    char pc = (char)malloc(5);
    FreeAndNull(&pc);
    _Analysis_assume_(pc == NULL);
    f(pc);
}
```

## <a name="see-also"></a>Zobacz także

- [__assume](../intrinsics/assume.md)
