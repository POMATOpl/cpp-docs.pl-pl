---
description: 'Dowiedz się więcej na temat: _heapadd'
title: _heapadd
ms.date: 11/04/2016
api_name:
- _heapadd
api_location:
- msvcr100.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr80.dll
- msvcrt.dll
- msvcr110.dll
- msvcr90.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- heapadd
- _heapadd
helpviewer_keywords:
- _heapadd function
- memory, adding to heaps
- heaps, adding memory
- heapadd function
ms.assetid: 4d691fe2-2763-49f4-afb1-62738b7cd3ff
ms.openlocfilehash: 0270f84de2c543e37f089418b833011c2d83230d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97120685"
---
# <a name="_heapadd"></a>_heapadd

Dodaje pamięć do sterty.

> [!IMPORTANT]
> Ta funkcja jest przestarzała. Począwszy od programu Visual Studio 2015, nie jest on dostępny w CRT.

## <a name="syntax"></a>Składnia

```
int _heapadd(
   void *memblock,
   size_t size
);
```

#### <a name="parameters"></a>Parametry

*memblock*<br/>
Wskaźnik do pamięci sterty.

*zmienia*<br/>
Rozmiar pamięci do dodania w bajtach.

## <a name="return-value"></a>Wartość zwracana

Jeśli to się powiedzie, `_heapadd` zwraca 0; w przeciwnym razie funkcja zwraca-1 i ustawia `errno` jako `ENOSYS` .

Aby uzyskać więcej informacji na temat tego i innych kodów powrotnych, zobacz [_doserrno, errno, _sys_errlist i _sys_nerr](../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Uwagi

Począwszy od Visual C++ wersji 4,0, źródłowa struktura sterty została przeniesiona do bibliotek uruchomieniowych C, aby obsługiwała nowe funkcje debugowania. W związku z tym program `_heapadd` nie jest już obsługiwany na żadnej platformie, która jest oparta na Win32 API.

## <a name="requirements"></a>Wymagania

|Procedura|Wymagany nagłówek|Opcjonalny nagłówek|
|-------------|---------------------|---------------------|
|`_heapadd`|\<malloc.h>|\<errno.h>|

Aby uzyskać więcej informacji o zgodności, zobacz temat [zgodność](../c-runtime-library/compatibility.md) we wprowadzeniu.

## <a name="see-also"></a>Zobacz też

[Alokacja pamięci](../c-runtime-library/memory-allocation.md)<br/>
[zwolniony](../c-runtime-library/reference/free.md)<br/>
[_heapchk](../c-runtime-library/reference/heapchk.md)<br/>
[_heapmin](../c-runtime-library/reference/heapmin.md)<br/>
[_heapset](../c-runtime-library/heapset.md)<br/>
[_heapwalk](../c-runtime-library/reference/heapwalk.md)<br/>
[malloc](../c-runtime-library/reference/malloc.md)<br/>
[realloc](../c-runtime-library/reference/realloc.md)
