---
description: 'Dowiedz się więcej na temat: _aligned_free'
title: _aligned_free
ms.date: 4/2/2020
api_name:
- _aligned_free
- _o__aligned_free
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
- api-ms-win-crt-heap-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- aligned_free
- _aligned_free
helpviewer_keywords:
- _aligned_free function
- aligned_free function
ms.assetid: ed1ce952-cdfc-4682-85cc-f75d4101603d
ms.openlocfilehash: 2efbda028f1a5c23ce8a6f02da543a114534985d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97303729"
---
# <a name="_aligned_free"></a>_aligned_free

Zwalnia blok pamięci, który został przydzielony do [_aligned_malloc](aligned-malloc.md) lub [_aligned_offset_malloc](aligned-offset-malloc.md).

## <a name="syntax"></a>Składnia

```C
void _aligned_free (
   void *memblock
);
```

### <a name="parameters"></a>Parametry

*memblock*<br/>
Wskaźnik do bloku pamięci, który został zwrócony do `_aligned_malloc` `_aligned_offset_malloc` funkcji or.

## <a name="remarks"></a>Uwagi

**_aligned_free** jest oznaczona `__declspec(noalias)` , co oznacza, że funkcja nie modyfikuje zmiennych globalnych. Aby uzyskać więcej informacji, zobacz [noalias](../../cpp/noalias.md).

Ta funkcja nie sprawdza poprawności jego parametru, w przeciwieństwie do innych _aligned funkcje CRT. Jeśli *memblock* jest wskaźnikiem typu null, ta funkcja po prostu nie wykonuje żadnych działań. Nie zmienia i nie `errno` wywołuje procedury obsługi nieprawidłowego parametru. Jeśli wystąpi błąd w funkcji, z powodu braku funkcji _aligned wcześniej do przydzielenia bloku pamięci lub nieprawidłowego wyrównania pamięci z powodu niektórych nieprzewidzianych Calamity, funkcja generuje raport debugowania z [_RPT, _RPTF, _RPTW, _RPTFW makra](rpt-rptf-rptw-rptfw-macros.md).

Domyślnie globalny stan tej funkcji jest objęty zakresem aplikacji. Aby to zmienić, zobacz [stan globalny w CRT](../global-state.md).

## <a name="requirements"></a>Wymagania

|Procedura|Wymagany nagłówek|
|-------------|---------------------|
|**_aligned_free**|\<malloc.h>|

## <a name="example"></a>Przykład

Aby uzyskać więcej informacji, zobacz [_aligned_malloc](aligned-malloc.md).

## <a name="see-also"></a>Zobacz też

[Wyrównanie danych](../../c-runtime-library/data-alignment.md)
