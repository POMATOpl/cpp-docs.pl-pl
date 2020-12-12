---
description: 'Dowiedz się więcej o: wyrównaniu danych'
title: Wyrównywanie danych
ms.date: 11/04/2016
f1_keywords:
- data.alignment
helpviewer_keywords:
- data alignment [C++]
ms.assetid: 35ac3d2d-a4b3-421b-954f-b7372b1f18e1
ms.openlocfilehash: cd942d0ec9c4cdfbedf473bf005123061dece669
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97326353"
---
# <a name="data-alignment"></a>Wyrównywanie danych

Poniższe funkcje uruchomieniowe języka C obsługują wyrównanie danych.

## <a name="data-alignment-routines"></a>Procedury Data-Alignment

|Procedura|Zastosowanie|
|-------------|---------|
|[_aligned_free](../c-runtime-library/reference/aligned-free.md)|Zwalnia blok pamięci, który został przydzielony do [_aligned_malloc](../c-runtime-library/reference/aligned-malloc.md)lub [_aligned_offset_malloc](../c-runtime-library/reference/aligned-offset-malloc.md).|
|[_aligned_free_dbg](../c-runtime-library/reference/aligned-free-dbg.md)|Zwalnia blok pamięci, który został przydzielony do [_aligned_malloc](../c-runtime-library/reference/aligned-malloc.md) lub [_aligned_offset_malloc](../c-runtime-library/reference/aligned-offset-malloc.md) (tylko debugowanie).|
|[_aligned_malloc](../c-runtime-library/reference/aligned-malloc.md)|Przydziela pamięć na określonej granicy wyrównania.|
|[_aligned_malloc_dbg](../c-runtime-library/reference/aligned-malloc-dbg.md)|Przydziela pamięć na określonej granicy wyrównania z dodatkowym miejscem dla nagłówka debugowania i buforów zastąpień (tylko wersja do debugowania).|
|[_aligned_msize](../c-runtime-library/reference/aligned-msize.md)|Zwraca rozmiar bloku pamięci przydzieloną w stercie.|
|[_aligned_msize_dbg](../c-runtime-library/reference/aligned-msize-dbg.md)|Zwraca rozmiar bloku pamięci przydzieloną w stercie (tylko wersja do debugowania).|
|[_aligned_offset_malloc](../c-runtime-library/reference/aligned-offset-malloc.md)|Przydziela pamięć na określonej granicy wyrównania.|
|[_aligned_offset_malloc_dbg](../c-runtime-library/reference/aligned-offset-malloc-dbg.md)|Przydziela pamięć na określonej granicy wyrównania (tylko w wersji do debugowania).|
|[_aligned_offset_realloc](../c-runtime-library/reference/aligned-offset-realloc.md)|Zmienia rozmiar bloku pamięci, który został przydzielony do [_aligned_malloc](../c-runtime-library/reference/aligned-malloc.md) lub [_aligned_offset_malloc](../c-runtime-library/reference/aligned-offset-malloc.md).|
|[_aligned_offset_realloc_dbg](../c-runtime-library/reference/aligned-offset-realloc-dbg.md)|Zmienia rozmiar bloku pamięci, który został przydzielony do [_aligned_malloc](../c-runtime-library/reference/aligned-malloc.md) lub [_aligned_offset_malloc](../c-runtime-library/reference/aligned-offset-malloc.md) (tylko wersja do debugowania).|
|[_aligned_offset_recalloc](../c-runtime-library/reference/aligned-offset-recalloc.md)|Zmienia rozmiar bloku pamięci, który został przydzielony do [_aligned_malloc](../c-runtime-library/reference/aligned-malloc.md) lub [_aligned_offset_malloc](../c-runtime-library/reference/aligned-offset-malloc.md) i inicjuje pamięć do 0.|
|[_aligned_offset_recalloc_dbg](../c-runtime-library/reference/aligned-offset-recalloc-dbg.md)|Zmienia rozmiar bloku pamięci, który został przydzielony do [_aligned_malloc](../c-runtime-library/reference/aligned-malloc.md) lub [_aligned_offset_malloc](../c-runtime-library/reference/aligned-offset-malloc.md) i inicjuje pamięć do 0 (tylko wersja do debugowania).|
|[_aligned_realloc](../c-runtime-library/reference/aligned-realloc.md)|Zmienia rozmiar bloku pamięci, który został przydzielony do [_aligned_malloc](../c-runtime-library/reference/aligned-malloc.md) lub [_aligned_offset_malloc](../c-runtime-library/reference/aligned-offset-malloc.md).|
|[_aligned_realloc_dbg](../c-runtime-library/reference/aligned-realloc-dbg.md)|Zmienia rozmiar bloku pamięci, który został przydzielony do [_aligned_malloc](../c-runtime-library/reference/aligned-malloc.md) lub [_aligned_offset_malloc](../c-runtime-library/reference/aligned-offset-malloc.md) (tylko wersja do debugowania).|
|[_aligned_recalloc](../c-runtime-library/reference/aligned-recalloc.md)|Zmienia rozmiar bloku pamięci, który został przydzielony do [_aligned_malloc](../c-runtime-library/reference/aligned-malloc.md) lub [_aligned_offset_malloc](../c-runtime-library/reference/aligned-offset-malloc.md) i inicjuje pamięć do 0.|
|[_aligned_recalloc_dbg](../c-runtime-library/reference/aligned-recalloc-dbg.md)|Zmienia rozmiar bloku pamięci, który został przydzielony do [_aligned_malloc](../c-runtime-library/reference/aligned-malloc.md) lub [_aligned_offset_malloc](../c-runtime-library/reference/aligned-offset-malloc.md) i inicjuje pamięć do 0 (tylko wersja do debugowania).|

## <a name="see-also"></a>Zobacz też

[Procedury środowiska uruchomieniowego języka Universal C według kategorii](../c-runtime-library/run-time-routines-by-category.md)<br/>
