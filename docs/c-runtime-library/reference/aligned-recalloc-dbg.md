---
description: 'Dowiedz się więcej na temat: _aligned_recalloc_dbg'
title: _aligned_recalloc_dbg
ms.date: 11/04/2016
api_name:
- _aligned_recalloc_dbg
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
- _aligned_recalloc_dbg
- aligned_recalloc_dbg
helpviewer_keywords:
- aligned_recalloc_dbg function
- _aligned_recalloc_dbg function
ms.assetid: 55c3c27e-561c-4d6b-9bf9-1e34cc556e4b
ms.openlocfilehash: bfe0450f4a1b63f7451ff148b183c94f59002efc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97135736"
---
# <a name="_aligned_recalloc_dbg"></a>_aligned_recalloc_dbg

Zmienia rozmiar bloku pamięci, który został przydzielony do [_aligned_malloc](aligned-malloc.md) lub [_aligned_offset_malloc](aligned-offset-malloc.md) i inicjuje pamięć do 0 (tylko wersja do debugowania).

## <a name="syntax"></a>Składnia

```C
void * _aligned_recalloc_dbg(
   void * memblock,
   size_t num,
   size_t size,
   size_t alignment,
   const char *filename,
   int linenumber
);
```

### <a name="parameters"></a>Parametry

*memblock*<br/>
Bieżący wskaźnik bloku pamięci.

*Liczba*<br/>
Liczba elementów.

*zmienia*<br/>
Rozmiar w bajtach każdego elementu.

*struktury*<br/>
Wartość wyrównania, która musi być całkowitą potęgą liczby 2.

*Nazwa pliku*<br/>
Wskaźnik na nazwę pliku źródłowego, który żądał operacji alokacji lub **ma wartość null**.

*LineNumber*<br/>
Numer wiersza w pliku źródłowym, w którym zażądano operacji alokacji lub **ma wartość null**.

## <a name="return-value"></a>Wartość zwracana

**_aligned_recalloc_dbg** zwraca wskaźnik void do ponownie przydzielony blok pamięci (i prawdopodobnie przeniesiony). Wartość zwracana ma wartość **null** , jeśli rozmiar ma wartość zero, a argument buforu nie ma **wartości null** lub jeśli nie ma wystarczającej ilości dostępnej pamięci, aby rozszerzyć blok na dany rozmiar. W pierwszym przypadku, oryginalny blok jest zwolniony. W drugim przypadku oryginalny blok nie zmienia się. Wartość zwracana wskazuje miejsce do magazynowania, które jest gwarantowane odpowiednio wyrównane do przechowywania dowolnego typu obiektu. Aby uzyskać wskaźnik do typu innego niż void, należy użyć rzutowania typu dla zwracanej wartości.

Wystąpił błąd podczas ponownego przydzielenia pamięci i zmiany wyrównania bloku.

## <a name="remarks"></a>Uwagi

**_aligned_recalloc_dbg** jest wersją debugowania funkcji [_aligned_recalloc](aligned-recalloc.md) . Gdy [_DEBUG](../../c-runtime-library/debug.md) nie jest zdefiniowany, każde wywołanie **_aligned_recalloc_dbg** zostanie zredukowane do wywołania **_aligned_recalloc**. Zarówno **_aligned_recalloc** , jak i **_aligned_recalloc_dbg** ponownie przydzielić blok pamięci w stercie podstawowym, ale **_aligned_recalloc_dbg** obsługuje kilka funkcji debugowania: bufory po obu stronach części bloku, aby przetestować pod kątem przecieków, a następnie *filename* / *LineNumber* informacji w celu określenia pochodzenia żądań alokacji. Śledzenie określonych typów alokacji przy użyciu parametru typu bloku nie jest obsługiwaną funkcją debugowania dla wyrównanych przydziałów. Wyrównane alokacje będą wyświetlane jako _NORMAL_BLOCK typ bloku.

**_aligned_recalloc_dbg** ponownie przydzieli określony blok pamięci o nieco większym rozmiarze niż żądany rozmiar (  *  *rozmiar* numeru), który może być większy lub mniejszy niż rozmiar pierwotnie przydzielonego bloku pamięci. Dodatkowe miejsce jest używane przez menedżera stosu debugowania, do łączenia bloków pamięci debugowania i do dostarczenia aplikacji informacji nagłówka debugowania i zastąpienia buforów. Ponowna Alokacja może spowodować przeniesienie oryginalnego bloku pamięci do innej lokalizacji w stercie, a także zmianę rozmiaru bloku pamięci. Część użytkownika bloku jest wypełniana wartością 0xCD, a bufory zastąpień są wypełnione 0xFD.

**_aligned_recalloc_dbg** ustawia **errno** na **ENOMEM** , jeśli alokacja pamięci nie powiedzie się; **EINVAL** jest zwracany, jeśli ilość wymaganej pamięci (łącznie z podaną wcześniej obciążeniem) przekracza **_HEAP_MAXREQ**. Aby uzyskać informacje o tym i innych kodach błędów, zobacz [errno, _doserrno, _sys_errlist i _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Ponadto **_aligned_recalloc_dbg** sprawdza poprawność jego parametrów. Jeśli *wyrównanie* nie jest potęgą liczby 2, ta funkcja wywołuje procedurę obsługi nieprawidłowego parametru, zgodnie z opisem w [walidacji parametru](../../c-runtime-library/parameter-validation.md). Jeśli wykonanie może być kontynuowane, ta funkcja zwraca **wartość null** i ustawia **errno** na **EINVAL**.

Aby uzyskać informacje o tym, jak bloki pamięci są przydzielane, inicjowane i zarządzane w wersji debugowania sterty podstawowej, zobacz [szczegóły sterty debugowania CRT](/visualstudio/debugger/crt-debug-heap-details). Aby uzyskać informacje o typach bloków alokacji i sposobach ich użycia, zobacz [typy bloków na stercie debugowania](/visualstudio/debugger/crt-debug-heap-details). Aby uzyskać informacje o różnicach między wywołaniem standardowej funkcji sterty i jej wersji debugowania w kompilacji debugowania aplikacji, zobacz [debugowanie wersji funkcji alokacji sterty](/visualstudio/debugger/debug-versions-of-heap-allocation-functions).

## <a name="requirements"></a>Wymagania

|Procedura|Wymagany nagłówek|
|-------------|---------------------|
|**_aligned_recalloc_dbg**|\<crtdbg.h>|

Aby uzyskać więcej informacji o zgodności, zobacz [zgodność](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Biblioteki

Debuguj wersje wyłącznie [bibliotek uruchomieniowych C](../../c-runtime-library/crt-library-features.md) .

## <a name="see-also"></a>Zobacz też

[Procedury debugowania](../../c-runtime-library/debug-routines.md)<br/>
