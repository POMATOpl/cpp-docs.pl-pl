---
description: 'Dowiedz się więcej na temat: efektów ubocznych'
title: Efekty uboczne
ms.date: 11/04/2016
helpviewer_keywords:
- expression evaluation, side effects
- side effects in expression evaluation
ms.assetid: d9b3004a-830e-43a0-bea5-8989d501d670
ms.openlocfilehash: 78a08cb2c6290a3cb9c0c61a714cb2bcfe61a4cc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97292783"
---
# <a name="side-effects"></a>Efekty uboczne

Kolejność obliczania wyrażeń jest definiowana przez określoną implementację, z wyjątkiem sytuacji, gdy język gwarantuje określoną kolejność oceny (zgodnie z [pierwszeństwem i kolejnością oceny](../c-language/precedence-and-order-of-evaluation.md)). Na przykład efekty uboczne występują w następujących wywołaniach funkcji:

```
add( i + 1, i = j + 2 );
myproc( getc(), getc() );
```

Argumenty wywołania funkcji można ocenić w dowolnej kolejności. Wyrażenie `i + 1` może być oceniane przed `i = j + 2` , lub `i = j + 2` może być oceniane przed `i + 1` . W każdym przypadku wynik jest różny. Podobnie nie jest możliwe zagwarantowanie, jakie znaki są faktycznie przesyłane do `myproc` . Ponieważ operacje przyrostu jednoargumentowego i zmniejszania obejmują przydziały, operacje te mogą powodować efekty uboczne, jak pokazano w następującym przykładzie:

```
x[i] = i++;
```

W tym przykładzie wartość `x` modyfikowana jest nieprzewidywalne. Wartość indeksu dolnego może być nową lub starą wartością `i` . Wyniki mogą się różnić w zależności od różnych kompilatorów lub różnych poziomów optymalizacji.

Ponieważ C nie definiuje kolejności oceny efektów ubocznych, obie metody oceny omówione powyżej są poprawne i mogą być zaimplementowane. Aby upewnić się, że kod jest przenośny i czysty, należy unikać instrukcji, które są zależne od określonej kolejności oceny efektów ubocznych.

## <a name="see-also"></a>Zobacz też

[Obliczanie wyrażeń](../c-language/expression-evaluation-c.md)
