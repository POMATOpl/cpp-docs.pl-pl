---
description: 'Dowiedz się więcej na temat: _strdup_dbg, _wcsdup_dbg'
title: _strdup_dbg, _wcsdup_dbg
ms.date: 11/04/2016
api_name:
- _strdup_dbg
- _wcsdup_dbg
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
- _wcsdup_dbg
- strdup_dbg
- _strdup_dbg
- wcsdup_dbg
helpviewer_keywords:
- _wcsdup_dbg function
- stdup_dbg function
- copying strings
- duplicating strings
- strings [C++], copying
- strings [C++], duplicating
- _strdup_dbg function
- wcsdup_dbg function
ms.assetid: 681db70c-d124-43ab-b83e-5eeea9035097
ms.openlocfilehash: c7001d7948f733977213267fdabd9faee4ddffd4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97322484"
---
# <a name="_strdup_dbg-_wcsdup_dbg"></a>_strdup_dbg, _wcsdup_dbg

Wersje [_strdup i _wcsdup](strdup-wcsdup-mbsdup.md) używające **wersji.**

## <a name="syntax"></a>Składnia

```C
char *_strdup_dbg(
   const char *strSource,
   int blockType,
   const char *filename,
   int linenumber
);
wchar_t *_wcsdup_dbg(
   const wchar_t *strSource,
   int blockType,
   const char *filename,
   int linenumber
);
```

### <a name="parameters"></a>Parametry

*strSource*<br/>
Ciąg źródłowy zakończony wartością null.

*BlockType*<br/>
Żądany typ bloku pamięci: **_CLIENT_BLOCK** lub **_NORMAL_BLOCK**.

*Nazwa pliku*<br/>
Wskaźnik na nazwę pliku źródłowego, który żądał operacji alokacji lub **ma wartość null**.

*LineNumber*<br/>
Numer wiersza w pliku źródłowym, w którym zażądano operacji alokacji lub **ma ona wartość null**.

## <a name="return-value"></a>Wartość zwracana

Każda z tych funkcji zwraca wskaźnik do lokalizacji magazynu dla skopiowanego ciągu lub **wartości null** , jeśli nie można przydzielić magazynu.

## <a name="remarks"></a>Uwagi

**_Strdup_dbg** i **_wcsdup_dbg** funkcje są takie same jak **_strdup** i **_wcsdup** , z wyjątkiem tego, że w przypadku zdefiniowania **_DEBUG** te funkcje używają wersji do debugowania, która **_malloc_dbg** **, do** przydzielenia pamięci dla zduplikowanego ciągu. Aby uzyskać informacje na temat funkcji debugowania **_malloc_dbg**, zobacz [_malloc_dbg](malloc-dbg.md).

Nie trzeba jawnie wywoływać tych funkcji w większości przypadków. Zamiast tego można zdefiniować flagę **_CRTDBG_MAP_ALLOC**. Gdy **_CRTDBG_MAP_ALLOC** jest zdefiniowany, wywołania **_strdup** i **_wcsdup** są ponownie mapowane do **_strdup_dbg** i **_wcsdup_dbg**, z ustawieniem *BlockType* na **_NORMAL_BLOCK**. W ten sposób nie trzeba wywoływać tych funkcji jawnie, chyba że chcesz oznaczyć bloki sterty jako **_CLIENT_BLOCK**. Aby uzyskać więcej informacji na temat typów bloków, zobacz [typy bloków na stercie debugowania](/visualstudio/debugger/crt-debug-heap-details).

### <a name="generic-text-routine-mappings"></a>Mapowania procedur zwykłego tekstu

|Procedura TCHAR.H|Nie zdefiniowano _MBCS _UNICODE &|_MBCS zdefiniowano|_UNICODE zdefiniowano|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcsdup_dbg**|**_strdup_dbg**|**_mbsdup**|**_wcsdup_dbg**|

## <a name="requirements"></a>Wymagania

|Procedura|Wymagany nagłówek|
|-------------|---------------------|
|**_strdup_dbg**, **_wcsdup_dbg**|\<crtdbg.h>|

Aby uzyskać dodatkowe informacje o zgodności, zobacz [zgodność](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Biblioteki

Wszystkie wersje debugowania [bibliotek uruchomieniowych C](../../c-runtime-library/crt-library-features.md).

## <a name="see-also"></a>Zobacz też

[Manipulowanie ciągami](../../c-runtime-library/string-manipulation-crt.md)<br/>
[_strdup, _wcsdup, _mbsdup](strdup-wcsdup-mbsdup.md)<br/>
[Wersje debugowania funkcji alokacji sterty](/visualstudio/debugger/debug-versions-of-heap-allocation-functions)<br/>
