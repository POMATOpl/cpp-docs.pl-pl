---
description: 'Dowiedz się więcej: wywoływanie przykładu funkcji prototypu i wywołania'
title: 'Przykład wywołania: prototyp funkcji i wywołanie'
ms.date: 11/04/2016
helpviewer_keywords:
- calling conventions, examples [C++]
- examples [C++], calling conventions
ms.assetid: e4275d1f-df2e-4bfc-a162-eb43ec69554a
ms.openlocfilehash: d7d8b68abc030e12d10fc5daa8b56f793d3ea14a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97335590"
---
# <a name="calling-example-function-prototype-and-call"></a>Przykład wywołania: prototyp funkcji i wywołanie

**Specyficzne dla firmy Microsoft**

Poniższy przykład pokazuje wyniki wykonywania wywołania funkcji przy użyciu różnych konwencji wywoływania.

Ten przykład jest oparty na poniższym szkieletzie funkcji. Zamień `calltype` na odpowiednią konwencję wywoływania.

```cpp
void    calltype MyFunc( char c, short s, int i, double f );
.
.
.
void    MyFunc( char c, short s, int i, double f )
    {
    .
    .
    .
    }
.
.
.
MyFunc ('x', 12, 8192, 2.7183);
```

Aby uzyskać więcej informacji, zobacz [wyniki wywołania przykładu](../cpp/results-of-calling-example.md).

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Konwencje wywoływania](../cpp/calling-conventions.md)
