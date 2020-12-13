---
description: 'Dowiedz się więcej na temat: _aligned_offset_malloc_dbg'
title: _aligned_offset_malloc_dbg
ms.date: 11/04/2016
api_name:
- _aligned_offset_malloc_dbg
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
- _aligned_offset_malloc_dbg
- aligned_offset_malloc_dbg
helpviewer_keywords:
- _aligned_offset_malloc_dbg function
- aligned_offset_malloc_dbg function
ms.assetid: 6c242307-c59e-4d63-aae5-d8cbec8e021c
ms.openlocfilehash: 1d8ae12e62ec1ea335a8bca554e07a0b64a3c3a5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336549"
---
# <a name="_aligned_offset_malloc_dbg"></a>_aligned_offset_malloc_dbg

Przydziela pamięć na określonej granicy wyrównania (tylko w wersji do debugowania).

## <a name="syntax"></a>Składnia

```C
void * _aligned_offset_malloc_dbg(
   size_t size,
   size_t alignment,
   size_t offset,
   const char *filename,
   int linenumber
);
```

### <a name="parameters"></a>Parametry

*zmienia*<br/>
Rozmiar alokacji żądanej pamięci.

*struktury*<br/>
Wartość wyrównania, która musi być całkowitą potęgą liczby 2.

*Przesunięcie*<br/>
Przesunięcie alokacji pamięci, aby wymusić wyrównanie.

*Nazwa pliku*<br/>
Wskaźnik na nazwę pliku źródłowego, który zażądał operacji alokacji lub **ma wartość null**.

*LineNumber*<br/>
Numer wiersza w pliku źródłowym, w którym zażądano operacji alokacji lub **ma wartość null**.

## <a name="return-value"></a>Wartość zwracana

Wskaźnik do bloku pamięci, który został przydzielony lub **ma wartość null** , jeśli operacja nie powiodła się.

## <a name="remarks"></a>Uwagi

**_aligned_offset_malloc_dbg** jest wersją debugowania funkcji [_aligned_offset_malloc](aligned-offset-malloc.md) . Gdy [_DEBUG](../../c-runtime-library/debug.md) nie jest zdefiniowany, każde wywołanie **_aligned_offset_malloc_dbg** zostanie zredukowane do wywołania **_aligned_offset_malloc**. Zarówno **_aligned_offset_malloc** , jak i **_aligned_offset_malloc_dbg** przydzielą blok pamięci w stercie podstawowej, ale **_aligned_offset_malloc_dbg** oferuje kilka funkcji debugowania: bufory po obu stronach części bloku, aby przetestować pod kątem przecieków, a następnie *filename* / *LineNumber* informacji w celu określenia pochodzenia żądań alokacji. Śledzenie określonych typów alokacji przy użyciu parametru typu bloku nie jest obsługiwaną funkcją debugowania dla wyrównanych przydziałów. Wyrównane alokacje będą wyświetlane jako _NORMAL_BLOCK typ bloku.

**_aligned_offset_malloc_dbg** przydziela blok pamięci z nieco większym miejscem niż żądany *rozmiar*. Dodatkowe miejsce jest używane przez menedżera stosu debugowania, do łączenia bloków pamięci debugowania i do dostarczenia aplikacji informacji nagłówka debugowania i zastąpienia buforów. Gdy blok zostanie przydzielony, część użytkownika bloku jest wypełniania wartościami 0xCD a każdy bufor zastąpienia jest wypełniany wartościami 0xFD.

**_aligned_offset_malloc_dbg** jest przydatne w sytuacjach, gdy jest potrzebne wyrównanie w zagnieżdżonym elemencie; na przykład jeśli w klasie zagnieżdżonej jest wymagana wartość wyrównania.

**_aligned_offset_malloc_dbg** jest oparta na **malloc**; Aby uzyskać więcej informacji, zobacz [malloc](malloc.md).

Ta funkcja ustawia **errno** na **ENOMEM** , jeśli alokacja pamięci nie powiodła się lub żądany rozmiar był większy niż **_HEAP_MAXREQ**. Aby uzyskać więcej informacji na temat **errno**, zobacz [errno, _doserrno, _sys_errlist i _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md). Ponadto **_aligned_offset_malloc** sprawdza poprawność jego parametrów. Jeśli *wyrównanie* nie jest potęgą 2 lub jeśli *przesunięcie* jest większe niż lub równe *rozmiarowi* i zero, ta funkcja wywołuje procedurę obsługi nieprawidłowego parametru, zgodnie z opisem w [walidacji parametru](../../c-runtime-library/parameter-validation.md). Jeśli wykonanie może być kontynuowane, ta funkcja zwraca **wartość null** i ustawia **errno** na **EINVAL**.

Aby uzyskać informacje o tym, jak bloki pamięci są przydzielane, inicjowane i zarządzane w wersji debugowania sterty podstawowej, zobacz [szczegóły sterty debugowania CRT](/visualstudio/debugger/crt-debug-heap-details).

Aby uzyskać informacje o typach bloków alokacji i sposobach ich użycia, zobacz [typy bloków na stercie debugowania](/visualstudio/debugger/crt-debug-heap-details).

## <a name="requirements"></a>Wymagania

|Procedura|Wymagany nagłówek|
|-------------|---------------------|
|**_aligned_offset_malloc_dbg**|\<crtdbg.h>|

Aby uzyskać więcej informacji o zgodności, zobacz [zgodność](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Biblioteki

Debuguj wersje wyłącznie [bibliotek uruchomieniowych C](../../c-runtime-library/crt-library-features.md) .

## <a name="see-also"></a>Zobacz też

[Procedury debugowania](../../c-runtime-library/debug-routines.md)<br/>
