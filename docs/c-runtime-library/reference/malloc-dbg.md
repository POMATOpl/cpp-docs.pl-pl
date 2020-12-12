---
description: 'Dowiedz się więcej na temat: _malloc_dbg'
title: _malloc_dbg
ms.date: 11/04/2016
api_name:
- _malloc_dbg
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
- malloc_dbg
- _malloc_dbg
helpviewer_keywords:
- malloc_dbg function
- memory allocation
- _malloc_dbg function
ms.assetid: c97eca51-140b-4461-8bd2-28965b49ecdb
ms.openlocfilehash: 56b39ecbbe5f90d9eee378d4ce42016e5960ff63
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97299816"
---
# <a name="_malloc_dbg"></a>_malloc_dbg

Przydziela blok pamięci w stercie z dodatkowym miejscem dla nagłówka debugowania i buforów zastąpień (tylko wersja do debugowania).

## <a name="syntax"></a>Składnia

```C
void *_malloc_dbg(
   size_t size,
   int blockType,
   const char *filename,
   int linenumber
);
```

### <a name="parameters"></a>Parametry

*zmienia*<br/>
Żądany rozmiar bloku pamięci (w bajtach).

*BlockType*<br/>
Żądany typ bloku pamięci: **_CLIENT_BLOCK** lub **_NORMAL_BLOCK**.

*Nazwa pliku*<br/>
Wskaźnik na nazwę pliku źródłowego, który zażądał operacji alokacji lub **ma wartość null**.

*LineNumber*<br/>
Numer wiersza w pliku źródłowym, w którym zażądano operacji alokacji lub **ma wartość null**.

Parametry *filename* i *LineNumber* są dostępne tylko wtedy, gdy **_malloc_dbg** została wywołana jawnie lub została zdefiniowana stała preprocesora [_CRTDBG_MAP_ALLOC](../../c-runtime-library/crtdbg-map-alloc.md) .

## <a name="return-value"></a>Wartość zwracana

Po pomyślnym zakończeniu funkcja ta zwraca wskaźnik do części użytkownika przydzielony blok pamięci, wywołuje nową funkcję obsługi lub zwraca **wartość null**. Pełny opis zachowania zwrotnego znajduje się w sekcji poniższe uwagi. Aby uzyskać więcej informacji o sposobie używania nowej funkcji obsługi, zobacz Funkcja [malloc](malloc.md) .

## <a name="remarks"></a>Uwagi

**_malloc_dbg** jest wersją debugowania funkcji [malloc](malloc.md) . Gdy [_DEBUG](../../c-runtime-library/debug.md) nie jest zdefiniowany, każde wywołanie **_malloc_dbg** zostanie zredukowane do wywołania **malloc**. Zarówno **malloc** , jak i **_malloc_dbg** przydzielają blok pamięci w stercie bazowym, ale **_malloc_dbg** oferuje kilka funkcji debugowania: bufory po obu stronach części bloku, aby przetestować pod kątem przecieków, parametr typu bloku służący do śledzenia określonych typów *alokacji i* / *LineNumber* informacji w celu określenia pochodzenia żądań alokacji.

**_malloc_dbg** przydziela blok pamięci z nieco większym miejscem niż żądany *rozmiar*. Dodatkowe miejsce jest używane przez menedżera stosu debugowania, do łączenia bloków pamięci debugowania i do dostarczenia aplikacji informacji nagłówka debugowania i zastąpienia buforów. Gdy blok zostanie przydzielony, część użytkownika bloku jest wypełniania wartościami 0xCD a każdy bufor zastąpienia jest wypełniany wartościami 0xFD.

**_malloc_dbg** ustawia **errno** na **ENOMEM** , jeśli alokacja pamięci nie powiedzie się lub jeśli wymagana ilość pamięci (łącznie z powyższym obciążeniem) przekracza **_HEAP_MAXREQ**. Aby uzyskać informacje o tym i innych kodach błędów, zobacz [errno, _doserrno, _sys_errlist i _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Aby uzyskać informacje o tym, jak bloki pamięci są przydzielane, inicjowane i zarządzane w wersji debugowania sterty podstawowej, zobacz [szczegóły sterty debugowania CRT](/visualstudio/debugger/crt-debug-heap-details). Aby uzyskać informacje o typach bloków alokacji i sposobach ich użycia, zobacz [typy bloków na stercie debugowania](/visualstudio/debugger/crt-debug-heap-details). Aby uzyskać informacje o różnicach między wywołaniem standardowej funkcji sterty i jej wersji debugowania w kompilacji debugowania aplikacji, zobacz [debugowanie wersji funkcji alokacji sterty](/visualstudio/debugger/debug-versions-of-heap-allocation-functions).

## <a name="requirements"></a>Wymagania

|Procedura|Wymagany nagłówek|
|-------------|---------------------|
|**_malloc_dbg**|\<crtdbg.h>|

Aby uzyskać więcej informacji o zgodności, zobacz [zgodność](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Biblioteki

Debuguj wersje wyłącznie [bibliotek uruchomieniowych C](../../c-runtime-library/crt-library-features.md) .

## <a name="example"></a>Przykład

Przykład używania **_malloc_dbg** można znaleźć w temacie [crt_dbg1](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/crt/crt_dbg1).

## <a name="see-also"></a>Zobacz też

[Procedury debugowania](../../c-runtime-library/debug-routines.md)<br/>
[malloc](malloc.md)<br/>
[_calloc_dbg](calloc-dbg.md)<br/>
