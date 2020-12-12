---
description: 'Dowiedz się więcej na temat: While — Instrukcja (C)'
title: while — instrukcja (C)
ms.date: 11/04/2016
f1_keywords:
- while
helpviewer_keywords:
- while keyword [C]
- while keyword [C], syntax
ms.assetid: d0c970b8-12a9-4827-afb2-a051111834b7
ms.openlocfilehash: 3461372de48980a0591f890fdd366c9373aea78f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97221855"
---
# <a name="while-statement-c"></a>while — instrukcja (C)

**`while`** Instrukcja pozwala powtórzyć instrukcję do momentu, gdy określone wyrażenie przyjmie wartość false.

## <a name="syntax"></a>Składnia

*iteracja — instrukcja*:<br/>
&nbsp;&nbsp;&nbsp;&nbsp;**while (***wyrażenie***)**—*instrukcja*      

*Wyrażenie* musi mieć typ arytmetyczny lub wskaźnikowy. Wykonanie przebiega w następujący sposób:

1. *Wyrażenie* jest oceniane.

1. Jeśli *wyrażenie* jest początkowo fałszywe, treść **`while`** instrukcji nigdy nie jest wykonywana, a kontrola przebiega z **`while`** instrukcji do następnej instrukcji w programie.

   Jeśli *wyrażenie* jest prawdziwe (niezerowe), treść instrukcji jest wykonywana i proces jest powtarzany, rozpoczynając od kroku 1.

**`while`** Instrukcja może również kończyć się, gdy **`break`** **`goto`** jest wykonywana, lub **`return`** w obrębie treści instrukcji. Użyj **`continue`** instrukcji, aby zakończyć iterację bez kończenia **`while`** pętli. **`continue`** Instrukcja przekazuje formant do następnej iteracji **`while`** instrukcji.

Jest to przykład **`while`** instrukcji:

```C
while ( i >= 0 )
{
    string1[i] = string2[i];
    i--;
}
```

Ten przykład kopiuje znaki z `string2` do `string1` . Jeśli `i` jest większy lub równy 0, `string2[i]` jest przypisywany do `string1[i]` i `i` jest zmniejszany. Gdy `i` osiągnie lub spadnie poniżej 0, wykonywanie **`while`** instrukcji zostaje przerwane.

## <a name="see-also"></a>Zobacz też

[While — Instrukcja (C++)](../cpp/while-statement-cpp.md)
