---
title: _ftell_nolock, _ftelli64_nolock
ms.date: 4/2/2020
api_name:
- _ftelli64_nolock
- _ftell_nolock
- _o__ftell_nolock
- _o__ftelli64_nolock
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
- api-ms-win-crt-stdio-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _ftelli64_nolock
- ftelli64_nolock
- ftell_nolock
- _ftell_nolock
helpviewer_keywords:
- ftelli64_nolock function
- _ftelli64_nolock function
- _ftell_nolock function
- ftell_nolock function
- file pointers [C++], getting current position
ms.assetid: 84e68b0a-32f8-4c4a-90ad-3f2387685ede
ms.openlocfilehash: fc6534daaeb3818e28e3c48dbc6d1d9586b6429e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/14/2020
ms.locfileid: "81345591"
---
# <a name="_ftell_nolock-_ftelli64_nolock"></a>_ftell_nolock, _ftelli64_nolock

Pobiera bieżącej pozycji wskaźnika pliku, bez blokowania wątku.

## <a name="syntax"></a>Składnia

```C
long _ftell_nolock(
   FILE *stream
);
__int64 _ftelli64_nolock(
   FILE *stream
);
```

### <a name="parameters"></a>Parametry

*Strumienia*<br/>
Kierowanie na strukturę **FILE.**

## <a name="return-value"></a>Wartość zwracana

Tak samo jak **ftell** i **_ftelli64**. Aby uzyskać więcej informacji, zobacz [ftell, _ftelli64](ftell-ftelli64.md).

## <a name="remarks"></a>Uwagi

Funkcje te są nieblokujące wersje **ftell** i **_ftelli64,** odpowiednio. Są one identyczne **z ftell** i **_ftelli64** z tą różnicą, że nie są chronione przed zakłóceniami przez inne wątki. Te funkcje mogą być szybsze, ponieważ nie ponoszą narzutu blokowania innych wątków. Użyj tych funkcji tylko w kontekstach bezpiecznych dla wątków, takich jak aplikacje jednowątkowe lub gdzie zakres wywołujący obsługuje już izolację wątku.

Domyślnie stan globalny tej funkcji jest ograniczony do aplikacji. Aby to zmienić, zobacz [Stan globalny w crt](../global-state.md).

## <a name="requirements"></a>Wymagania

|Funkcja|Wymagany nagłówek|Opcjonalny nagłówek|
|--------------|---------------------|---------------------|
|**ftell_nolock**|\<stdio.h>|\<> errno.h|
|**_ftelli64_nolock**|\<stdio.h>|\<> errno.h|

Aby uzyskać więcej informacji o zgodności, zobacz [Zgodność](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Zobacz też

[We/Wy strumienia](../../c-runtime-library/stream-i-o.md)<br/>
[fgetpos](fgetpos.md)<br/>
[fseek, _fseeki64](fseek-fseeki64.md)<br/>
[_lseek, _lseeki64](lseek-lseeki64.md)<br/>
[ftell, _ftelli64](ftell-ftelli64.md)<br/>
