---
title: Alokacja pamięci
ms.date: 11/04/2016
description: Wyświetla listę funkcji środowiska uruchomieniowego języka Microsoft C służących do przydzielania, zwalniania i ponownego przydzielenia pamięci.
f1_keywords:
- c.memory
helpviewer_keywords:
- memory allocation, routines
- memory, managing
- memory, allocation
ms.assetid: b4470556-a128-4782-9943-2ccf7a7d9979
ms.openlocfilehash: 4e01d62fdfd24416f78254a849b3feea97883281
ms.sourcegitcommit: 8caaf5e00aeb727741a273aecafa15de293426cf
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/07/2020
ms.locfileid: "91806503"
---
# <a name="memory-allocation"></a>Alokacja pamięci

Te procedury służą do przydzielania, wolnej i ponownej alokacji pamięci.

## <a name="memory-allocation-routines"></a>Procedury alokacji pamięci

|Procedura|Zastosowanie|
|-------------|---------|
|[_alloca](../c-runtime-library/reference/alloca.md), [_malloca](../c-runtime-library/reference/malloca.md)|Przydziel pamięć ze stosu|
|[calloc](../c-runtime-library/reference/calloc.md)|Przydziel magazyn dla tablicy, inicjując każdy bajt w przydzielonym bloku na 0|
|[_calloc_dbg](../c-runtime-library/reference/calloc-dbg.md)|Debuguj wersję **calloc**; dostępne tylko w wersjach debugowania bibliotek czasu wykonywania|
|[Usuwanie operatora,&#91;&#93;operatora delete ](../c-runtime-library/delete-operator-crt.md)|Bezpłatny przydzielony blok|
|[_expand](../c-runtime-library/reference/expand.md)|Rozwijanie lub zmniejszanie bloku pamięci bez przechodzenia|
|[_expand_dbg](../c-runtime-library/reference/expand-dbg.md)|Debuguj wersję **_expand**; dostępne tylko w wersjach debugowania bibliotek czasu wykonywania|
|[zwolniony](../c-runtime-library/reference/free.md)|Bezpłatny przydzielony blok|
|[_free_dbg](../c-runtime-library/reference/free-dbg.md)|Wersja do debugowania **bezpłatna**; dostępne tylko w wersjach debugowania bibliotek czasu wykonywania|
|[_freea](../c-runtime-library/reference/freea.md)|Bezpłatny przydzielony blok ze stosu|
|[_get_heap_handle](../c-runtime-library/reference/get-heap-handle.md)|Pobierz uchwyt Win32 sterty CRT.|
|[_heapadd](../c-runtime-library/heapadd.md)|Dodaj pamięć do sterty|
|[_heapchk](../c-runtime-library/reference/heapchk.md)|Sprawdź stertę pod kątem spójności|
|[_heapmin](../c-runtime-library/reference/heapmin.md)|Zwolnij nieużywaną pamięć w stercie|
|[_heapset](../c-runtime-library/heapset.md)|Wypełnij wolne wpisy sterty o określonej wartości|
|[_heapwalk](../c-runtime-library/reference/heapwalk.md)|Zwróć informacje o każdym wpisie na stercie|
|[malloc](../c-runtime-library/reference/malloc.md)|Przydziel blok pamięci z sterty|
|[_malloc_dbg](../c-runtime-library/reference/malloc-dbg.md)|Wersja debugowania funkcji **malloc**; dostępne tylko w wersjach debugowania bibliotek czasu wykonywania|
|[_msize](../c-runtime-library/reference/msize.md)|Zwrotny rozmiar przydzielnego bloku|
|[_msize_dbg](../c-runtime-library/reference/msize-dbg.md)|Debuguj wersję **_msize**; dostępne tylko w wersjach debugowania bibliotek czasu wykonywania|
|[nowe, nowe&#91;&#93;](../c-runtime-library/new-operator-crt.md)|Przydziel blok pamięci z sterty|
|[_query_new_handler](../c-runtime-library/reference/query-new-handler.md)|Adres zwrotny bieżącej nowej procedury obsługi zgodnie z ustawieniem **_set_new_handler**|
|[_query_new_mode](../c-runtime-library/reference/query-new-mode.md)|Zwróć liczbę całkowitą wskazującą nowy tryb obsługi ustawiony przez **_set_new_mode** dla usługi **malloc**|
|[realloc](../c-runtime-library/reference/realloc.md)|Przydziel ponownie blok do nowego rozmiaru|
|[_realloc_dbg](../c-runtime-library/reference/realloc-dbg.md)|Wersja debugowania **realloc**; dostępne tylko w wersjach debugowania bibliotek czasu wykonywania|
|[_set_new_handler](../c-runtime-library/reference/set-new-handler.md)|Włącz mechanizm obsługi błędów, gdy **`new`** operator zakończy się niepowodzeniem (aby przydzielić pamięć) i włączyć kompilację standardowych bibliotek C++|
|[_set_new_mode](../c-runtime-library/reference/set-new-mode.md)|Ustaw nowy tryb obsługi dla opcji **malloc**|

## <a name="see-also"></a>Zobacz też

[Procedury środowiska uruchomieniowego języka Universal C według kategorii](../c-runtime-library/run-time-routines-by-category.md)<br/>
