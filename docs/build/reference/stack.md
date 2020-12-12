---
description: Dowiedz się więcej na temat:/STACK
title: /STACK
ms.date: 11/04/2016
f1_keywords:
- /stack_editbin
helpviewer_keywords:
- -STACK editbin option
- STACK editbin option
- stack, setting size
- /STACK editbin option
ms.assetid: a39bcff0-c945-4355-80cc-8e4f24a5f142
ms.openlocfilehash: 253aec1d760a85f1ebe5dbf7596353b46744cd57
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97224455"
---
# <a name="stack"></a>/STACK

```
/STACK:reserve[,commit]
```

## <a name="remarks"></a>Uwagi

Ta opcja ustawia rozmiar stosu w bajtach i przyjmuje argumenty w notacji dziesiętnej lub w języku C. Opcja/STACK ma zastosowanie tylko do pliku wykonywalnego.

Argument *rezerwy* określa całkowitą alokację stosu w pamięci wirtualnej. POLECENIA EDITBIN zaokrągla określoną wartość do najbliższych 4 bajtów.

Opcjonalny `commit` argument podlega interpretacji przez system operacyjny. W systemie Windows NT, Windows 95 i Windows 98 `commit` określa ilość pamięci fizycznej do przydzielenia w danym momencie. Przydzielona pamięć wirtualna powoduje, że miejsce jest zarezerwowane w pliku stronicowania. Wyższa `commit` wartość oszczędza czas, gdy aplikacja wymaga większej ilości miejsca w stosie, ale zwiększa wymagania dotyczące pamięci i czas uruchamiania.

## <a name="see-also"></a>Zobacz też

[Opcje polecenia EDITBIN](editbin-options.md)
