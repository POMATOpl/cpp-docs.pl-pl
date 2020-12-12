---
description: 'Dowiedz się więcej o: umieszczanie, _putws'
title: puts, _putws
ms.date: 4/2/2020
api_name:
- _putws
- puts
- _o__putws
- _o_puts
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
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _putts
- _putws
- puts
helpviewer_keywords:
- strings [C++], writing
- _putts function
- standard output, writing to
- putws function
- puts function
- putts function
- _putws function
ms.assetid: 32dada12-ed45-40ac-be06-3feeced9ecd6
ms.openlocfilehash: 9b48be23b02301f79b942371fbd273a14bab3800
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97268954"
---
# <a name="puts-_putws"></a>puts, _putws

Zapisuje ciąg w strumieniu **stdout**.

## <a name="syntax"></a>Składnia

```C
int puts(
   const char *str
);
int _putws(
   const wchar_t *str
);
```

### <a name="parameters"></a>Parametry

*str*<br/>
Ciąg wyjściowy.

## <a name="return-value"></a>Wartość zwracana

Zwraca wartość nieujemną, jeśli powodzenie. Jeśli **umieszczenie** nie powiedzie się, zwraca **znacznik EOF**; Jeśli **_putws** nie powiedzie się, zwraca **WEOF**. Jeśli *str* jest pustym wskaźnikiem, zostanie wywołana procedura obsługi nieprawidłowego parametru, zgodnie z opisem w [walidacji parametru](../../c-runtime-library/parameter-validation.md). Jeśli wykonanie może być kontynuowane, funkcje ustawiają **errno** na **EINVAL** i zwracają **EOF** lub **WEOF**.

Aby uzyskać informacje o tych i innych kodach błędów, zobacz [_doserrno, errno, _sys_errlist i _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Uwagi

Funkcja **Put** zapisuje *str* do standardowego strumienia wyjściowego **stdout**, zastępując znak kończący null ciągu ("\ 0") znakiem nowego wiersza ("\n") w strumieniu wyjściowym.

**_putws** to wersja znaku dwubajtowego **umieszczania**; dwie funkcje zachowują się identycznie, jeśli strumień jest otwarty w trybie ANSI. **umieszczenie** nie obsługuje obecnie danych wyjściowych w strumieniu Unicode.

**_putwch** zapisuje znaki Unicode przy użyciu bieżących ustawień regionalnych konsoli.

Domyślnie globalny stan tej funkcji jest objęty zakresem aplikacji. Aby to zmienić, zobacz [stan globalny w CRT](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Mapowania procedur zwykłego tekstu

|Procedura TCHAR.H|Nie zdefiniowano _MBCS _UNICODE &|_MBCS zdefiniowano|_UNICODE zdefiniowano|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_putts**|**sumaryczn**|**sumaryczn**|**_putws**|

## <a name="requirements"></a>Wymagania

|Procedura|Wymagany nagłówek|
|-------------|---------------------|
|**sumaryczn**|\<stdio.h>|
|**_putws**|\<stdio.h>|

Konsola nie jest obsługiwana w aplikacjach platforma uniwersalna systemu Windows (platformy UWP). Standardowe uchwyty strumienia, które są skojarzone z konsolą, **stdin**, **stdout** i **stderr**, muszą zostać przekierowane przed użyciem funkcji języka C w aplikacjach platformy UWP. Aby uzyskać dodatkowe informacje o zgodności, zobacz [zgodność](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Biblioteki

Wszystkie wersje [bibliotek uruchomieniowych języka C](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Przykład

```C
// crt_puts.c
// This program uses puts to write a string to stdout.

#include <stdio.h>

int main( void )
{
   puts( "Hello world from puts!" );
}
```

### <a name="output"></a>Dane wyjściowe

```Output
Hello world from puts!
```

## <a name="see-also"></a>Zobacz też

[We/Wy strumienia](../../c-runtime-library/stream-i-o.md)<br/>
[fputs, fputws](fputs-fputws.md)<br/>
[fgets, fgetws](fgets-fgetws.md)<br/>
