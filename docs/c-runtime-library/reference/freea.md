---
description: 'Dowiedz się więcej na temat: _freea'
title: _freea
ms.date: 11/04/2016
api_name:
- _freea
api_location:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- freea
- _freea
helpviewer_keywords:
- _freea function
- freea function
- memory deallocation
ms.assetid: dcd30584-dd9d-443b-8c4c-13237a1cecac
ms.openlocfilehash: 6d6f57117265e62e7d3c822110b52f69cb65ffac
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97282968"
---
# <a name="_freea"></a>_freea

Cofa alokację lub zwalnia blok pamięci.

## <a name="syntax"></a>Składnia

```C
void _freea(
   void *memblock
);
```

### <a name="parameters"></a>Parametry

*memblock*<br/>
Wcześniej przydzielono blok pamięci, który ma zostać zwolniony.

## <a name="return-value"></a>Wartość zwracana

Brak.

## <a name="remarks"></a>Uwagi

Funkcja **_freea** rozdziela blok pamięci (*memblock*), który został wcześniej przydzielony przez wywołanie do [_malloca](malloca.md). **_freea** sprawdza, czy pamięć została przypisana na stercie lub na stosie. Jeśli została przypisana na stosie, **_freea** nic nie robi. Jeśli została przypisana na stercie, liczba zwolnionych bajtów jest równoważna z liczbą bajtów żądaną podczas przydzielenia bloku. Jeśli *memblock* ma **wartość null**, wskaźnik jest ignorowany i **_freea** natychmiast zwraca. Próba zwolnienia nieprawidłowego wskaźnika (wskaźnik do bloku pamięci, który nie został przydzielony przez **_malloca**) może mieć wpływ na kolejne żądania alokacji i powodować błędy.

**_freea** wywołuje **bezpłatnie** wewnętrznie, jeśli stwierdzi, że pamięć jest alokowana na stercie. Czy pamięć znajduje się na stercie, czy stos jest określany przez znacznik umieszczony w pamięci pod adresem bezpośrednio poprzedzającym przydzieloną pamięć.

Jeśli wystąpi błąd podczas zwalniania pamięci, **errno** jest ustawiany z informacjami z systemu operacyjnego w przypadku awarii. Aby uzyskać więcej informacji, zobacz [errno, _doserrno, _sys_errlist i _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Po zwolnieniu bloku pamięci [_heapmin](heapmin.md) minimalizuje ilość wolnej pamięci w stercie przez podzbiór nieużywanych regionów i zwolnienie ich z powrotem do systemu operacyjnego. Zwolniona pamięć, która nie została wydana w systemie operacyjnym, zostaje przywrócona do puli bezpłatna i ponownie dostępna do przydzielenia.

Wywołanie **_freea** musi towarzyszyć wszystkim wywołań do **_malloca**. Występuje również błąd do wywołania **_freea** dwa razy w tej samej pamięci. Gdy aplikacja jest połączona z wersją debugową bibliotek uruchomieniowych C, szczególnie w przypadku funkcji [_malloc_dbg](malloc-dbg.md) włączonych przez zdefiniowanie **_CRTDBG_MAP_ALLOC**, łatwiej jest znaleźć brakujące lub zduplikowane wywołania do **_freea**. Aby uzyskać więcej informacji na temat sposobu zarządzania sterty podczas procesu debugowania, zobacz [sterta debugowania CRT](/visualstudio/debugger/crt-debug-heap-details).

**_freea** jest oznaczona `__declspec(noalias)` , co oznacza, że funkcja nie modyfikuje zmiennych globalnych. Aby uzyskać więcej informacji, zobacz [noalias](../../cpp/noalias.md).

## <a name="requirements"></a>Wymagania

|Funkcja|Wymagany nagłówek|
|--------------|---------------------|
|**_freea**|\<stdlib.h> i \<malloc.h>|

Aby uzyskać więcej informacji o zgodności, zobacz [zgodność](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Przykład

Zapoznaj się z przykładem [_malloca](malloca.md).

## <a name="see-also"></a>Zobacz też

[Alokacja pamięci](../../c-runtime-library/memory-allocation.md)<br/>
[_malloca](malloca.md)<br/>
[calloc](calloc.md)<br/>
[malloc](malloc.md)<br/>
[_malloc_dbg](malloc-dbg.md)<br/>
[realloc](realloc.md)<br/>
[_free_dbg](free-dbg.md)<br/>
[_heapmin](heapmin.md)<br/>
