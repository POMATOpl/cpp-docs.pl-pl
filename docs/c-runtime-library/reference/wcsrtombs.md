---
description: 'Dowiedz się więcej na temat: wcsrtombs'
title: wcsrtombs
ms.date: 4/2/2020
api_name:
- wcsrtombs
- _o_wcsrtombs
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
- api-ms-win-crt-convert-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- wcsrtombs
helpviewer_keywords:
- wcsrtombs function
- string conversion, wide characters
- wide characters, strings
ms.assetid: a8d21fec-0d36-4085-9d81-9b1c61c7259d
ms.openlocfilehash: 34fabe44c0e239eba4201b180df026655a4277f4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340515"
---
# <a name="wcsrtombs"></a>wcsrtombs

Przekonwertuj ciąg znaków dwubajtowych na reprezentację w postaci ciągu znaków. Dostępna jest bezpieczniejsza wersja tej funkcji; Zobacz [wcsrtombs_s](wcsrtombs-s.md).

## <a name="syntax"></a>Składnia

```C
size_t wcsrtombs(
   char *mbstr,
   const wchar_t **wcstr,
   sizeof count,
   mbstate_t *mbstate
);
template <size_t size>
size_t wcsrtombs(
   char (&mbstr)[size],
   const wchar_t **wcstr,
   sizeof count,
   mbstate_t *mbstate
); // C++ only
```

### <a name="parameters"></a>Parametry

*mbstr*<br/>
W wyniku konwersji lokalizacja adresu ciągu znaków wielobajtowych.

*wcstr*<br/>
Pośrednio wskazuje lokalizację ciągu znaków dwubajtowych do przekonwertowania.

*liczbą*<br/>
Liczba znaków do przekonwertowania.

*mbstate*<br/>
Wskaźnik do obiektu stanu konwersji **mbstate_t** .

## <a name="return-value"></a>Wartość zwracana

Zwraca liczbę pomyślnie przekonwertowanych bajtów, bez uwzględnienia końcowego bajtu o wartości null (jeśli istnieje), w przeciwnym razie a-1, jeśli wystąpił błąd.

## <a name="remarks"></a>Uwagi

Funkcja **wcsrtombs** konwertuje ciąg znaków dwubajtowych, zaczynając od określonego stanu konwersji zawartego w *mbstate*, z wartości pośrednich wskazanych w *wcstr* w adresie *mbstr*. Konwersja będzie kontynuowana dla każdego znaku do: po napotkaniu znaku dwubajtowego zakończenia o wartości null, gdy zostanie napotkany nieodpowiadający znak lub gdy następny znak spowodowałoby przekroczenie limitu zawartego w *Count*. Jeśli **wcsrtombs** napotka znak dwubajtowy o wartości null (L ' \ 0 ') przed lub w przypadku *występowania* , konwertuje go na 8-bitowy 0 i zatrzyma.

W ten sposób ciąg znaków wielobajtowych w *mbstr* jest zakończony wartością null tylko wtedy, gdy **wcsrtombs** napotka znak dwuznakowy o wartości null podczas konwersji. Jeśli sekwencje wskazywane przez *wcstr* i *mbstr* nakładają się na siebie, zachowanie **wcsrtombs** jest niezdefiniowane. **wcsrtombs** ma wpływ na kategorię LC_TYPE bieżących ustawień regionalnych.

Funkcja **wcsrtombs** różni się od [wcstombs, _wcstombs_l](wcstombs-wcstombs-l.md) według jej ponownego uruchomienia. Stan konwersji jest przechowywany w *mbstate* dla kolejnych wywołań do tych samych lub innych funkcji, które można uruchomić ponownie. Wyniki są niezdefiniowane podczas mieszania użycia funkcji ponownego uruchamiania i nieuruchomionych ponownie.  Na przykład aplikacja będzie używać **wcsrlen** zamiast **wcsnlen**, jeśli zamiast **wcstombs** użyto kolejnego wywołania **wcsrtombs** .

Jeśli argument *mbstr* ma **wartość null**, funkcja **wcsrtombs** zwraca wymagany rozmiar w bajtach ciągu docelowego. Jeśli *mbstate* ma wartość null, używany jest wewnętrzny stan konwersji **mbstate_t** . Jeśli *WCHAR* sekwencji znaków nie ma odpowiadającej reprezentacji znaków wielobajtowych, zwracana jest wartość-1, a **errno** jest ustawiona na **EILSEQ**.

W języku C++ ta funkcja ma Przeciążenie szablonu, które wywołuje nowszy, bezpieczny odpowiednik tej funkcji. Aby uzyskać więcej informacji, zobacz [bezpieczne przeciążenia szablonów](../../c-runtime-library/secure-template-overloads.md).

Domyślnie globalny stan tej funkcji jest objęty zakresem aplikacji. Aby to zmienić, zobacz [stan globalny w CRT](../global-state.md).

## <a name="exceptions"></a>Wyjątki

Funkcja **wcsrtombs** jest wielowątkowej bezpiecznie, o ile funkcja w bieżącym wątku nie wywołuje metody **setlocaling** , podczas gdy ta funkcja jest wykonywana, a *mbstate* nie jest równa null.

## <a name="example"></a>Przykład

```cpp
// crt_wcsrtombs.cpp
// compile with: /W3
// This code example converts a wide
// character string into a multibyte
// character string.

#include <stdio.h>
#include <memory.h>
#include <wchar.h>
#include <errno.h>

#define MB_BUFFER_SIZE 100

int main()
{
    const wchar_t   wcString[] =
                    {L"Every good boy does fine."};
    const wchar_t   *wcsIndirectString = wcString;
    char            mbString[MB_BUFFER_SIZE];
    size_t          countConverted;
    mbstate_t       mbstate;

    // Reset to initial shift state
    ::memset((void*)&mbstate, 0, sizeof(mbstate));

    countConverted = wcsrtombs(mbString, &wcsIndirectString,
                               MB_BUFFER_SIZE, &mbstate); // C4996
    // Note: wcsrtombs is deprecated; consider using wcsrtombs_s
    if (errno == EILSEQ)
    {
        printf( "An encoding error was detected in the string.\n" );
    }
    else
    {
        printf( "The string was successfuly converted.\n" );
    }
}
```

```Output
The string was successfuly converted.
```

## <a name="requirements"></a>Wymagania

|Procedura|Wymagany nagłówek|
|-------------|---------------------|
|**wcsrtombs**|\<wchar.h>|

## <a name="see-also"></a>Zobacz też

[Konwersja danych](../../c-runtime-library/data-conversion.md)<br/>
[Ustawienie](../../c-runtime-library/locale.md)<br/>
[Interpretacja sekwencji Multibyte-Character](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[wcrtomb](wcrtomb.md)<br/>
[wcrtomb_s](wcrtomb-s.md)<br/>
[wctomb, _wctomb_l](wctomb-wctomb-l.md)<br/>
[wcstombs, _wcstombs_l](wcstombs-wcstombs-l.md)<br/>
[mbsinit](mbsinit.md)<br/>
