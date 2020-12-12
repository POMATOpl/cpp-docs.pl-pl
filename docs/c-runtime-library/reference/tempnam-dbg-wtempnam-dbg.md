---
description: 'Dowiedz się więcej na temat: _tempnam_dbg, _wtempnam_dbg'
title: _tempnam_dbg, _wtempnam_dbg
ms.date: 11/04/2016
api_name:
- _wtempnam_dbg
- _tempnam_dbg
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
- wtempnam_dbg
- tempnam_dbg
- _tempnam_dbg
- _wtempnam_dbg
helpviewer_keywords:
- file names [C++], creating temporary
- tempnam_dbg function
- temporary files, creating
- file names [C++], temporary
- wtempnam_dbg function
- _tempnam_dbg function
- _wtempnam_dbg function
ms.assetid: e3760bb4-bb01-4808-b689-2c45af56a170
ms.openlocfilehash: 0f8788eb00d6cfd19f5675824838ce37e905b8ea
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97326213"
---
# <a name="_tempnam_dbg-_wtempnam_dbg"></a>_tempnam_dbg, _wtempnam_dbg

Wersje funkcji [_tempnam, _wtempnam, tmpnam _wtmpnam,](tempnam-wtempnam-tmpnam-wtmpnam.md) w których jest używana wersja do debugowania **malloc**, **_malloc_dbg**.

## <a name="syntax"></a>Składnia

```C
char *_tempnam_dbg(
   const char *dir,
   const char *prefix,
   int blockType,
   const char *filename,
   int linenumber
);
wchar_t *_wtempnam_dbg(
   const wchar_t *dir,
   const wchar_t *prefix,
   int blockType,
   const char *filename,
   int linenumber
);
```

### <a name="parameters"></a>Parametry

*katalogów*<br/>
Ścieżka użyta w nazwie pliku, jeśli nie istnieje zmienna środowiskowa TMP lub jeśli TMP nie jest prawidłowym katalogiem.

*prefiks*<br/>
Ciąg, który będzie wstępnie oczekiwał na nazwy zwrócone przez **_tempnam**.

*BlockType*<br/>
Żądany typ bloku pamięci: **_CLIENT_BLOCK** lub **_NORMAL_BLOCK**.

*Nazwa pliku*<br/>
Wskaźnik na nazwę pliku źródłowego, który żądał operacji alokacji lub **ma wartość null**.

*LineNumber*<br/>
Numer wiersza w pliku źródłowym, w którym zażądano operacji alokacji lub **ma ona wartość null**.

## <a name="return-value"></a>Wartość zwracana

Każda funkcja zwraca wskaźnik do wygenerowanej nazwy lub **wartości null** , jeśli wystąpi błąd. Błąd może wystąpić, jeśli w zmiennej środowiskowej TMP określono nieprawidłową nazwę katalogu i w parametrze *dir* .

> [!NOTE]
> **wolne** (lub **free_dbg**) musi zostać wywołane dla wskaźników przyznanych przez **_tempnam_dbg** i **_wtempnam_dbg**.

## <a name="remarks"></a>Uwagi

**_Tempnam_dbg** i **_wtempnam_dbg** funkcje są takie same jak **_tempnam** i **_wtempnam** , z wyjątkiem tego, że w przypadku zdefiniowania **_DEBUG** te funkcje używają wersji **i** **_malloc_dbg** debugowania, aby przydzielić pamięć, jeśli **wartość null** zostanie przeniesiona jako pierwszy parametr. Aby uzyskać więcej informacji, zobacz [_malloc_dbg](malloc-dbg.md).

Nie trzeba jawnie wywoływać tych funkcji w większości przypadków. Zamiast tego można zdefiniować flagę **_CRTDBG_MAP_ALLOC**. Gdy **_CRTDBG_MAP_ALLOC** jest zdefiniowany, wywołania **_tempnam** i **_wtempnam** są ponownie mapowane do **_tempnam_dbg** i **_wtempnam_dbg**, z ustawieniem *BlockType* na **_NORMAL_BLOCK**. W ten sposób nie trzeba wywoływać tych funkcji jawnie, chyba że chcesz oznaczyć bloki sterty jako **_CLIENT_BLOCK**. Aby uzyskać więcej informacji, zobacz [typy bloków na stercie debugowania](/visualstudio/debugger/crt-debug-heap-details).

### <a name="generic-text-routine-mappings"></a>Mapowania procedur zwykłego tekstu

|Procedura TCHAR.H|Nie zdefiniowano _MBCS _UNICODE &|_MBCS zdefiniowano|_UNICODE zdefiniowano|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_ttempnam_dbg**|**_tempnam_dbg**|**_tempnam_dbg**|**_wtempnam_dbg**|

## <a name="requirements"></a>Wymagania

|Procedura|Wymagany nagłówek|
|-------------|---------------------|
|**_tempnam_dbg**, **_wtempnam_dbg**|\<crtdbg.h>|

Aby uzyskać dodatkowe informacje o zgodności, zobacz [zgodność](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Zobacz też

[_tempnam, _wtempnam, tmpnam, _wtmpnam](tempnam-wtempnam-tmpnam-wtmpnam.md)<br/>
[We/Wy strumienia](../../c-runtime-library/stream-i-o.md)<br/>
[Wersje debugowania funkcji alokacji sterty](/visualstudio/debugger/debug-versions-of-heap-allocation-functions)<br/>
