---
description: 'Dowiedz się więcej na temat: GetChar, getwchar'
title: getchar, getwchar
ms.date: 06/23/2020
api_name:
- getchar
- getwchar
- _o_getchar
- _o_getwchar
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
- getwchar
- GetChar
helpviewer_keywords:
- gettchar function
- characters, reading
- getwchar function
- _gettchar function
- standard input, reading from
ms.assetid: 19fda588-3e33-415c-bb60-dd73c028086a
ms.openlocfilehash: d8480d179cc31d30d68c07fbe92bf389226ccd53
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97256760"
---
# <a name="getchar-getwchar"></a>getchar, getwchar

Odczytuje znak ze standardowego wejścia.

## <a name="syntax"></a>Składnia

```C
int getchar();
wint_t getwchar();
```

## <a name="return-value"></a>Wartość zwracana

Zwraca odczyt znaku. Te funkcje oczekują na wejście i nie zwracają do momentu udostępnienia danych wejściowych.

Aby wskazać błąd odczytu lub stan końca pliku, **GetChar** zwraca **EOF**, a **getwchar** zwraca **WEOF**. Dla elementu **GetChar** Użyj obiektu **odwołującego** lub **feof** , aby wyszukać błąd lub koniec pliku.

## <a name="remarks"></a>Uwagi

Każda procedura odczytuje pojedynczy znak z **stdin** i zwiększa skojarzony wskaźnik pliku, aby wskazywał na następny znak. **GetChar** jest taka sama jak [_fgetchar](fgetc-fgetwc.md), ale jest zaimplementowana jako funkcja i jako makro.

Te funkcje również blokują wątek wywołujący i są bezpieczne wątkowo. W przypadku wersji, która nie jest blokowana, zobacz [_getchar_nolock, _getwchar_nolock](getchar-nolock-getwchar-nolock.md).

Domyślnie globalny stan tej funkcji jest objęty zakresem aplikacji. Aby to zmienić, zobacz [stan globalny w CRT](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Mapowania procedur zwykłego tekstu

|Procedura TCHAR.H|Nie zdefiniowano _MBCS _UNICODE &|_MBCS zdefiniowano|_UNICODE zdefiniowano|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_gettchar**|**GetChar**|**GetChar**|**getwchar**|

## <a name="requirements"></a>Wymagania

|Procedura|Wymagany nagłówek|
|-------------|---------------------|
|**GetChar**|\<stdio.h>|
|**getwchar**|\<stdio.h> lub \<wchar.h>|

Konsola nie jest obsługiwana w aplikacjach platforma uniwersalna systemu Windows (platformy UWP). Standardowe uchwyty strumienia, które są skojarzone z konsolą, **stdin**, **stdout** i **stderr**, muszą zostać przekierowane przed użyciem funkcji języka C w aplikacjach platformy UWP. Aby uzyskać dodatkowe informacje o zgodności, zobacz [zgodność](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Przykład

```C
// crt_getchar.c
// Use getchar to read a line from stdin.

#include <stdio.h>

int main()
{
    char buffer[81];
    int i, ch;

    for (i = 0; (i < 80) && ((ch = getchar()) != EOF)
                         && (ch != '\n'); i++)
    {
        buffer[i] = (char) ch;
    }

    // Terminate string with a null character
    buffer[i] = '\0';
    printf( "Input was: %s\n", buffer);
}
```

```Output

This textInput was: This text
```

## <a name="see-also"></a>Zobacz także

[We/Wy strumienia](../../c-runtime-library/stream-i-o.md)<br/>
[getc, getwc](getc-getwc.md)<br/>
[fgetc, fgetwc](fgetc-fgetwc.md)<br/>
[_getch, _getwch](getch-getwch.md)<br/>
[putc, putwc](putc-putwc.md)<br/>
[ungetc, ungetwc](ungetc-ungetwc.md)<br/>
