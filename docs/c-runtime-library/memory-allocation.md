---
title: Alokacja pamięci
ms.date: 11/18/2020
description: Lista funkcji środowiska uruchomieniowego języka Microsoft C służących do przydzielania, zwalniania i ponownego przydzielania pamięci.
f1_keywords:
- c.memory
helpviewer_keywords:
- memory allocation, routines
- memory, managing
- memory, allocation
ms.openlocfilehash: 39be48a4ebdf8ee917395d7b743846196200878d
ms.sourcegitcommit: e82e13b80150fcb27a1387018aafb00d99a3827a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/19/2020
ms.locfileid: "94920745"
---
# <a name="memory-allocation"></a>Alokacja pamięci

Te procedury przydzielają, zwalniają i ponownie przydzielają pamięć.

## <a name="memory-allocation-routines"></a>Procedury alokacji pamięci

|Procedura|Zastosowanie|
|-------------|---------|
|[`_alloca`](../c-runtime-library/reference/alloca.md), [`_malloca`](../c-runtime-library/reference/malloca.md)|Przydziel pamięć ze stosu|
|[`calloc`](../c-runtime-library/reference/calloc.md)|Przydziel tablicę i zainicjuj jej elementy na 0 (zero)|
|[`_calloc_dbg`](../c-runtime-library/reference/calloc-dbg.md)|Debuguj wersję programu **`calloc`** . Dostępne tylko w wersjach debugowania bibliotek czasu wykonywania|
|[`operator delete`, `operator delete[]`](../c-runtime-library/delete-operator-crt.md)|Zwolnij pamięć przydzieloną na stercie |
|[`_expand`](../c-runtime-library/reference/expand.md)|Rozwijanie lub zmniejszanie bloku pamięci bez przechodzenia|
|[`_expand_dbg`](../c-runtime-library/reference/expand-dbg.md)|Debuguj wersję programu **`_expand`** . Dostępne tylko w wersjach debugowania bibliotek czasu wykonywania|
|[`free`](../c-runtime-library/reference/free.md)|Zwolnij pamięć przydzieloną na stercie|
|[`_free_dbg`](../c-runtime-library/reference/free-dbg.md)|Debuguj wersję programu **`free`** . Dostępne tylko w wersjach debugowania bibliotek czasu wykonywania|
|[`_freea`](../c-runtime-library/reference/freea.md)|Zwolnij pamięć przydzieloną na stosie|
|[`_get_heap_handle`](../c-runtime-library/reference/get-heap-handle.md)|Pobierz system Win32 `HANDLE` do sterty środowiska uruchomieniowego języka C (CRT).|
|[`_heapadd`](../c-runtime-library/heapadd.md)|Dodawanie pamięci do sterty|
|[`_heapchk`](../c-runtime-library/reference/heapchk.md)|Sprawdzanie spójności sterty|
|[`_heapmin`](../c-runtime-library/reference/heapmin.md)|Zwolnij nieużywaną pamięć w stercie|
|[`_heapset`](../c-runtime-library/heapset.md)|Wypełnij wolne wpisy sterty wartością|
|[`_heapwalk`](../c-runtime-library/reference/heapwalk.md)|Pobierz informacje o każdym wpisie w stercie|
|[`malloc`](../c-runtime-library/reference/malloc.md)|Przydziel pamięć ze sterty|
|[`_malloc_dbg`](../c-runtime-library/reference/malloc-dbg.md)|Wersja debugowania programu **`malloc`** ; dostępna tylko w wersjach debugowania bibliotek czasu wykonywania|
|[`_msize`](../c-runtime-library/reference/msize.md)|Zwraca rozmiar przydzielonych bloków pamięci|
|[`_msize_dbg`](../c-runtime-library/reference/msize-dbg.md)|Wersja debugowania programu **`_msize`** ; dostępna tylko w wersjach debugowania bibliotek czasu wykonywania|
|[`new`, `new[]`](../c-runtime-library/new-operator-crt.md)|Przydzielanie bloku pamięci ze sterty|
|[`_query_new_handler`](../c-runtime-library/reference/query-new-handler.md)|Pobierz adres bieżącej nowej procedury obsługi ustawionej przez **`_set_new_handler`**|
|[`_query_new_mode`](../c-runtime-library/reference/query-new-mode.md)|Pobierz nowy tryb obsługi ustawiony przez **`_set_new_mode`** dla programu **`malloc`**|
|[`realloc`](../c-runtime-library/reference/realloc.md)|Ponowne przydzielanie bloku do nowego rozmiaru|
|[`_realloc_dbg`](../c-runtime-library/reference/realloc-dbg.md)|Wersja debugowania programu **`realloc`** ; dostępna tylko w wersjach debugowania bibliotek czasu wykonywania|
|[`_set_new_handler`](../c-runtime-library/reference/set-new-handler.md)|Włączenie mechanizmu obsługi błędów **`new`** , gdy operator nie może przydzielić pamięci, i włączyć kompilację standardowych bibliotek C++|
|[`_set_new_mode`](../c-runtime-library/reference/set-new-mode.md)|Ustaw nowy tryb obsługi dla **`malloc`**|

## <a name="see-also"></a>Zobacz także

[Procedury środowiska uruchomieniowego języka Universal C według kategorii](../c-runtime-library/run-time-routines-by-category.md)