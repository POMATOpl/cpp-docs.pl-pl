---
description: 'Dowiedz się więcej na temat: ostatni znak w ciągu'
title: Ostatni znak w ciągu
ms.date: 11/04/2016
helpviewer_keywords:
- last character in string
- MBCS [C++], last character in string
ms.assetid: 0a180376-4e55-41e8-9c64-539c7b6d8047
ms.openlocfilehash: 10ab90614509508b9667c29ccf166ddaf784a92e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97207244"
---
# <a name="last-character-in-a-string"></a>Ostatni znak w ciągu

Skorzystaj z następujących wskazówek:

- Zakresy bajtów końcowych nakładają się na zestaw znaków ASCII w wielu przypadkach. Można bezpiecznie używać skanowania bytewise do dowolnych znaków kontrolnych (mniej niż 32).

- Rozważmy następujący wiersz kodu, który może sprawdzić, czy ostatni znak w ciągu jest znakiem ukośnika odwrotnego:

    ```cpp
    if ( sz[ strlen( sz ) - 1 ] == '\\' )    // Is last character a '\'?
        // . . .
    ```

   Ponieważ `strlen` nie jest MBCS, zwraca liczbę bajtów, a nie liczbę znaków w ciągu wielobajtowym. Należy również pamiętać, że na niektórych stronach kodowych (na przykład 932), " \\ " (0x5c) jest prawidłowym bajtem końcowym ( `sz` jest ciągiem C).

   Jednym z możliwych rozwiązań jest przepisanie kodu w ten sposób:

    ```cpp
    char *pLast;
    pLast = _mbsrchr( sz, '\\' );    // find last occurrence of '\' in sz
    if ( pLast && ( *_mbsinc( pLast ) == '\0' ) )
        // . . .
    ```

   Ten kod używa funkcji MBCS `_mbsrchr` i `_mbsinc` . Ponieważ te funkcje są oparte na MBCS, mogą rozróżnić znak "" \\ i bajt końcowy " \\ ". Kod wykonuje niektóre akcje, jeśli ostatni znak w ciągu jest wartością null (' \ 0 ').

## <a name="see-also"></a>Zobacz też

[Wskazówki dotyczące programowania MBCS](../text/mbcs-programming-tips.md)<br/>
[Przypisanie znaku](../text/character-assignment.md)
