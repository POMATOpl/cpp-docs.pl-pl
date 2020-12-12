---
description: Dowiedz się więcej na temat przechowywania literałów ciągów
title: Magazynowanie literałów ciągu
ms.date: 11/04/2016
helpviewer_keywords:
- string literals, storage
ms.assetid: ba5e4d2c-d456-44b3-a8ca-354af547ac50
ms.openlocfilehash: 5139d480af6b808b5b2e008500794d95d63a9980
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97205268"
---
# <a name="storage-of-string-literals"></a>Magazynowanie literałów ciągu

Znaki ciągu literału są przechowywane w kolejności w ciągłej lokalizacji pamięci. Sekwencja ucieczki (taka jak **\\\\** lub **\\ "**) w literale ciągu liczy jako pojedynczy znak. Znak null (reprezentowany przez sekwencję ucieczki **\ 0** ) jest automatycznie dołączany do i oznacza koniec każdego literału ciągu. (Dzieje się to w [fazie translacji](../preprocessor/phases-of-translation.md) 7). Należy zauważyć, że kompilator może nie przechowywać dwóch identycznych ciągów przy użyciu dwóch różnych adresów. [/GF](../build/reference/gf-eliminate-duplicate-strings.md) wymusza, aby kompilator umieszczał pojedynczą kopię identycznych ciągów w pliku wykonywalnym.

## <a name="remarks"></a>Uwagi

**Specyficzne dla firmy Microsoft**

Ciągi mają statyczny czas przechowywania. Zobacz [klasy magazynu](../c-language/c-storage-classes.md) , aby uzyskać informacje o czasie trwania magazynu.

**ZAKOŃCZENIE określonych przez firmę Microsoft**

## <a name="see-also"></a>Zobacz też

[Literały ciągu języka C](../c-language/c-string-literals.md)
