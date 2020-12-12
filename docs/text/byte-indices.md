---
description: 'Dowiedz się więcej o: indeksów bajtów'
title: Indeksy bajtowe
ms.date: 11/04/2016
helpviewer_keywords:
- MBCS [C++], byte indices
- byte indices [C++]
ms.assetid: f6e7774a-86c6-41c2-89e3-74fd46432e47
ms.openlocfilehash: 5ee4b2cb8611893c71f5c6597e619cc73e2848ef
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97187562"
---
# <a name="byte-indices"></a>Indeksy bajtowe

Skorzystaj z następujących wskazówek:

- Praca z indeksem bytewise w ciągu przedstawia problemy podobne do tych, które są powodowane przez manipulowanie wskaźnikami. Rozważmy ten przykład, który skanuje ciąg dla znaku ukośnika odwrotnego:

    ```cpp
    while ( rgch[ i ] != '\\' )
        i++;
    ```

   Może to spowodować indeksowanie bajtu końcowego, a nie bajtu wiodącego, co może oznaczać, że nie wskazuje na `character` .

- Użyj funkcji [_mbclen](../c-runtime-library/reference/mbclen-mblen-mblen-l.md) , aby rozwiązać poprzedni problem:

    ```cpp
    while ( rgch[ i ] != '\\' )
        i += _mbclen ( rgch + i );
    ```

   To prawidłowo indeksuje bajt wiodący, dlatego do `character` . `_mbclen`Funkcja określa rozmiar znaku (1 lub 2 bajty).

## <a name="see-also"></a>Zobacz też

[Wskazówki dotyczące programowania MBCS](../text/mbcs-programming-tips.md)<br/>
[Ostatni znak w ciągu](../text/last-character-in-a-string.md)
