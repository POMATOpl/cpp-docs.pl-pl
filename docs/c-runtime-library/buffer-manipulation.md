---
description: 'Dowiedz się więcej na temat: manipulowanie buforem'
title: Manipulowanie buforem
ms.date: 04/04/2018
helpviewer_keywords:
- buffers, manipulation routines
- buffers
ms.assetid: 164f4860-ce66-412c-8291-396fbd70f03e
ms.openlocfilehash: 8389faf1e2e3de44507784755c7b4831952b9ffe
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97221738"
---
# <a name="buffer-manipulation"></a>Manipulowanie buforem

Te procedury służą do pracy z obszarami pamięci w oparciu o bajt po bajcie.

## <a name="buffer-manipulation-routines"></a>Procedury manipulowania buforem

|Procedura|Zastosowanie|
|-------------|---------|
|[_memccpy](../c-runtime-library/reference/memccpy.md)|Kopiuj znaki z jednego buforu do innego do momentu skopiowania danego znaku lub podanej liczby znaków|
|[memchr, wmemchr](../c-runtime-library/reference/memchr-wmemchr.md)|Zwróć wskaźnik do pierwszego wystąpienia w określonej liczbie znaków, danego znaku w buforze|
|[memcmp, wmemcmp](../c-runtime-library/reference/memcmp-wmemcmp.md)|Porównaj określoną liczbę znaków z dwóch buforów|
|[memcpy, wmemcpy](../c-runtime-library/reference/memcpy-wmemcpy.md), [memcpy_s, wmemcpy_s](../c-runtime-library/reference/memcpy-s-wmemcpy-s.md)|Kopiuj określoną liczbę znaków z jednego buforu do innego|
|[_memicmp, _memicmp_l](../c-runtime-library/reference/memicmp-memicmp-l.md)|Porównaj określoną liczbę znaków z dwóch buforów bez względu na wielkość liter|
|[memmove, wmemmove](../c-runtime-library/reference/memmove-wmemmove.md),[memmove_s, wmemmove_s](../c-runtime-library/reference/memmove-s-wmemmove-s.md)|Kopiuj określoną liczbę znaków z jednego buforu do innego|
|[memset, wmemset](../c-runtime-library/reference/memset-wmemset.md)|Użyj danego znaku, aby zainicjować określoną liczbę bajtów w buforze|
|[_swab](../c-runtime-library/reference/swab.md)|Zamień bajty danych i Zapisz je w określonej lokalizacji|

Gdy obszary źródłowe i docelowe nakładają się na siebie, tylko **memmove** jest gwarantowane, że pełne źródło zostanie prawidłowo skopiowane.

## <a name="see-also"></a>Zobacz też

[Procedury środowiska uruchomieniowego języka Universal C według kategorii](../c-runtime-library/run-time-routines-by-category.md)
