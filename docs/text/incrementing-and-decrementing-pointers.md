---
description: Dowiedz się więcej o tym, jak zwiększać i zmniejszać wskaźniki
title: Inkrementacja i dekrementacja wskaźników
ms.date: 11/04/2016
helpviewer_keywords:
- incrementing pointers
- MBCS [C++], pointers
- pointers [C++], multibyte characters
- decrementing pointers
ms.assetid: 0872b4a0-e2bd-4004-8319-070efb76f2fd
ms.openlocfilehash: 3c333c11c5a0b68bf013dbd374eb1cc4e5f00abc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97207322"
---
# <a name="incrementing-and-decrementing-pointers"></a>Inkrementacja i dekrementacja wskaźników

Skorzystaj z następujących wskazówek:

- Wskazuje, że potencjalni klienci nie mają bajtów. Zwykle nie jest to bezpieczne posiadanie wskaźnika do bajtu końcowego. Zwykle bezpieczniejsze jest skanowanie ciągu do przodu, a nie odwrotnie.

- Istnieją funkcje zwiększania/zmniejszania wskaźnika i dostępne są makra przenoszone przez cały znak:

    ```cpp
    sz1++;
    ```

   Wartość  zostanie zmieniona na:

    ```cpp
    sz1 = _mbsinc( sz1 );
    ```

   `_mbsinc`I `_mbsdec` funkcje są poprawnie zwiększane i zmniejszane w `character` jednostkach, niezależnie od rozmiaru znaku.

- W przypadku zmniejszeń potrzebny jest wskaźnik do nagłówka ciągu, tak jak w poniższym:

    ```cpp
    sz2--;
    ```

   Wartość  zostanie zmieniona na:

    ```cpp
    sz2 = _mbsdec( sz2Head, sz2 );
    ```

   Alternatywnie, wskaźnik głowy może być prawidłowym znakiem w ciągu, tak że:

    ```cpp
    sz2Head < sz2
    ```

   Musisz mieć wskaźnik do znanego prawidłowego bajtu potencjalnego klienta.

- Możesz chcieć zachować wskaźnik do poprzedniego znaku w celu przyspieszenia wywołania do `_mbsdec` .

## <a name="see-also"></a>Zobacz też

[Wskazówki dotyczące programowania MBCS](../text/mbcs-programming-tips.md)<br/>
[Indeksy bajtów](../text/byte-indices.md)
