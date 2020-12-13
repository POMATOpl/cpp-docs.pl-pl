---
description: 'Dowiedz się więcej na temat: _aligned_msize_dbg'
title: _aligned_msize_dbg
ms.date: 11/04/2016
api_name:
- _aligned_msize_dbg
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
- _aligned_msize_dbg
helpviewer_keywords:
- _aligned_msize_dbg
ms.assetid: f1c44af0-3f66-4033-81d1-d71d3afecba0
ms.openlocfilehash: 37b21f5992db09b1b356191263788be4516decb6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97335675"
---
# <a name="_aligned_msize_dbg"></a>_aligned_msize_dbg

Zwraca rozmiar bloku pamięci przydzieloną w stercie (tylko wersja do debugowania).

## <a name="syntax"></a>Składnia

```C
size_t _aligned_msize_dbg(
   void *memblock,
   size_t alignment,
   size_t offset
);
```

### <a name="parameters"></a>Parametry

*memblock*<br/>
Wskaźnik do bloku pamięci.

*struktury*<br/>
Wartość wyrównania, która musi być całkowitą potęgą liczby 2.

*Przesunięcie*<br/>
Przesunięcie alokacji pamięci, aby wymusić wyrównanie.

## <a name="return-value"></a>Wartość zwracana

Zwraca rozmiar (w bajtach) jako liczbę całkowitą bez znaku.

## <a name="remarks"></a>Uwagi

Wartości *wyrównania* i *przesunięcia* muszą być takie same jak wartości przesyłane do funkcji, która przydzieliła blok.

**_aligned_msize_dbg** jest wersją debugowania funkcji [_aligned_msize](aligned-msize.md) . Gdy [_DEBUG](../../c-runtime-library/debug.md) nie jest zdefiniowany, każde wywołanie **_aligned_msize_dbg** zostanie zredukowane do wywołania **_aligned_msize**. Oba **_aligned_msize** i **_aligned_msize_dbg** obliczają rozmiar bloku pamięci w stercie podstawowej, ale **_aligned_msize_dbg** dodaje funkcję debugowania: zawiera bufory po obu stronach części bloku pamięci w zwróconym rozmiarze.

Ta funkcja sprawdza poprawność parametru. Jeśli *memblock* jest wskaźnikiem wartości null lub *wyrównaniem* nie jest potęgą liczby 2, **_msize** wywołuje procedurę obsługi nieprawidłowego parametru, zgodnie z opisem w [walidacji parametru](../../c-runtime-library/parameter-validation.md). Jeśli błąd jest obsługiwany, funkcja ustawia **errno** na **EINVAL** i zwraca wartość-1.

Aby uzyskać informacje o tym, jak bloki pamięci są przydzielane, inicjowane i zarządzane w wersji debugowania sterty podstawowej, zobacz [szczegóły sterty debugowania CRT](/visualstudio/debugger/crt-debug-heap-details). Aby uzyskać informacje o typach bloków alokacji i sposobach ich użycia, zobacz [typy bloków na stercie debugowania](/visualstudio/debugger/crt-debug-heap-details). Aby uzyskać informacje o różnicach między wywołaniem standardowej funkcji sterty i jej wersji debugowania w kompilacji debugowania aplikacji, zobacz [debugowanie wersji funkcji alokacji sterty](/visualstudio/debugger/debug-versions-of-heap-allocation-functions).

## <a name="requirements"></a>Wymagania

|Procedura|Wymagany nagłówek|
|-------------|---------------------|
|**_aligned_msize_dbg**|\<crtdbg.h>|

Aby uzyskać więcej informacji o zgodności, zobacz [zgodność](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Biblioteki

Debuguj wersje wyłącznie [bibliotek uruchomieniowych C](../../c-runtime-library/crt-library-features.md) .

## <a name="see-also"></a>Zobacz też

[Alokacja pamięci](../../c-runtime-library/memory-allocation.md)<br/>
