---
description: 'Dowiedz się więcej o: Instrukcja if (C)'
title: if — instrukcja (C)
ms.date: 11/04/2016
f1_keywords:
- else
- if
helpviewer_keywords:
- if keyword [C]
- else clauses
- else keyword [C]
- if keyword [C], if statement syntax
- nested statements
ms.assetid: d7fc16a0-fdbc-4f39-b596-76e1ca4ad4a5
ms.openlocfilehash: 07d350329d047e35948ed9819de640e98c5bc13b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97182141"
---
# <a name="if-statement-c"></a>if — instrukcja (C)

**`if`** Instrukcja kontroluje rozgałęzienie warunkowe. Treść **`if`** instrukcji jest wykonywana, jeśli wartość wyrażenia jest różna od zera. Składnia **`if`** instrukcji ma dwa formy.

## <a name="syntax"></a>Składnia

SELECT *-Statement*: **if (***wyrażenie***)***instrukcja*      

**if (***wyrażenie***)** instrukcja *instrukcji* **`else`**           

W obu formach **`if`** instrukcji, wyrażenia, które mogą mieć dowolną wartość z wyjątkiem struktury, są oceniane, łącznie ze wszystkimi efektami ubocznymi.

W pierwszej postaci składni, jeśli *wyrażenie* jest prawdziwe (niezerowe), *instrukcja* jest wykonywana. Jeśli *wyrażenie* ma wartość false, *instrukcja* jest ignorowana. W drugiej postaci składni, która używa **`else`** , druga *instrukcja* jest wykonywana, jeśli *wyrażenie* ma wartość false. W obu formularzach kontrolki są przekazywane z **`if`** instrukcji do następnej instrukcji w programie, chyba że jedna z instrukcji zawiera **`break`** , **`continue`** , lub **`goto`** .

Poniżej przedstawiono przykłady **`if`** instrukcji:

```C
if ( i > 0 )
    y = x / i;
else
{
    x = i;
    y = f( x );
}
```

W tym przykładzie instrukcja `y = x/i;` jest wykonywana, jeśli `i` jest większa niż 0. Jeśli `i` jest mniejsza lub równa 0, `i` jest przypisana do `x` i `f( x )` jest przypisywana do `y` . Należy zauważyć, że instrukcja tworząca **`if`** klauzulę kończącą się średnikiem.

Podczas zagnieżdżania **`if`** instrukcji i **`else`** klauzule, należy użyć nawiasów klamrowych, aby zgrupować instrukcje i klauzule do instrukcji złożonych, które wyjaśniają zamiar. Jeśli nie ma żadnych nawiasów klamrowych, kompilator rozpoznaje niejasności, kojarząc każdy **`else`** z najbliżej **`if`** **`else`** .

```C
if ( i > 0 )           /* Without braces */
    if ( j > i )
        x = j;
    else
        x = i;
```

**`else`** Klauzula jest skojarzona z wewnętrzną **`if`** instrukcją w tym przykładzie. Jeśli `i` jest mniejsza lub równa 0, żadna wartość nie jest przypisana do `x` .

```C
if ( i > 0 )
{                      /* With braces */
    if ( j > i )
        x = j;
}
else
    x = i;
```

Nawiasy klamrowe otaczające wewnętrzną **`if`** instrukcję w tym przykładzie tworzą **`else`** klauzulę instrukcji zewnętrznej **`if`** . Jeśli `i` jest mniejsza lub równa 0, `i` jest przypisana do `x` .

## <a name="see-also"></a>Zobacz też

[if-else — instrukcja (C++)](../cpp/if-else-statement-cpp.md)
