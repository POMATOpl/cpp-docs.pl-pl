---
description: 'Dowiedz się więcej na temat: _get_tzname'
title: _get_tzname
ms.date: 4/2/2020
api_name:
- _get_tzname
- _o__get_tzname
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
- api-ms-win-crt-time-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _get_tzname
- get_tzname
helpviewer_keywords:
- _get_tzname function
- time zones
- get_tzname function
ms.assetid: df0065ff-095f-4237-832c-2fe9ab913875
ms.openlocfilehash: b98a068d6f2d2643df43078c5a274fd761ac8e95
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97338949"
---
# <a name="_get_tzname"></a>_get_tzname

Pobiera ciąg znaków reprezentujący nazwę strefy czasowej lub nazwę czasową standardowej strefy czasowej (DST).

## <a name="syntax"></a>Składnia

```C
errno_t _get_tzname(
    size_t* pReturnValue,
    char* timeZoneName,
    size_t sizeInBytes,
    int index
);
```

### <a name="parameters"></a>Parametry

*pReturnValue*<br/>
Długość ciągu dla elementu *timeZoneName* uwzględniającego terminator o wartości null.

*Strefa czasowa*<br/>
Adres ciągu znaków dla reprezentacji nazwy strefy czasowej lub standardowej nazwy strefy czasowej (DST), w zależności od *indeksu*.

*sizeInBytes*<br/>
Rozmiar ciągu znaków *timeZoneName* w bajtach.

*indeks*<br/>
Indeks jednej z dwóch nazw stref czasowych do pobrania.

|*indeks*|Zawartość elementu *timeZoneName*|wartość domyślna *timeZoneName*|
|-|-|-|
|0|Nazwa strefy czasowej|KOPIA|
|1|Nazwa standardowej strefy czasowej|PDT|
|> 1 lub < 0|**errno** ustawiony na **EINVAL**|nie zmodyfikowano|

O ile wartości nie są jawnie zmieniane w czasie wykonywania, wartości domyślne to "PST" i "PDT".

## <a name="return-value"></a>Wartość zwracana

Zero, jeśli to się powiedzie, w przeciwnym razie wartość typu **errno** .

Jeśli wartość *timeZoneName* ma **wartość null** lub *sizeInBytes* jest równa zero lub mniejsza od zera (ale nie obu), wywoływana jest procedura obsługi nieprawidłowego parametru, zgodnie z opisem w [walidacji parametru](../../c-runtime-library/parameter-validation.md). Jeśli wykonanie może być kontynuowane, ta funkcja ustawia **errno** na **EINVAL** i zwraca **EINVAL**.

### <a name="error-conditions"></a>Warunki błędów

|*pReturnValue*|*Strefa czasowa*|*sizeInBytes*|*indeks*|Wartość zwracana|Zawartość elementu *timeZoneName*|
|--------------------|--------------------|-------------------|-------------|------------------|--------------------------------|
|rozmiar nazwy programu $|**NULL**|0|0 lub 1|0|nie zmodyfikowano|
|rozmiar nazwy programu $|dowolny|> 0|0 lub 1|0|Nazwa $|
|nie zmodyfikowano|**NULL**|> 0|dowolny|**EINVAL**|nie zmodyfikowano|
|nie zmodyfikowano|dowolny|zero|dowolny|**EINVAL**|nie zmodyfikowano|
|nie zmodyfikowano|dowolny|> 0|> 1|**EINVAL**|nie zmodyfikowano|

## <a name="remarks"></a>Uwagi

Funkcja **_get_tzname** Pobiera reprezentację ciągu znaków bieżącej nazwy strefy czasowej lub standardowej nazwy strefy czasowej (DST) do adresu *strefy* czasowej w zależności od wartości indeksu, wraz z rozmiarem ciągu w *pReturnValue*. Jeśli *timeZoneName* ma **wartość null** , a *sizeInBytes* ma wartość zero, rozmiar ciągu wymaganego do przechowywania określonej strefy czasowej i zakończenie wartości null w bajtach jest zwracany w *pReturnValue*. Wartości indeksu muszą mieć wartość 0 dla standardowej strefy czasowej lub 1 dla standardowej strefy czasowej (letnia). wszystkie inne wartości *indeksu* mają nieokreślony wynik.

Domyślnie globalny stan tej funkcji jest objęty zakresem aplikacji. Aby to zmienić, zobacz [stan globalny w CRT](../global-state.md).

## <a name="example"></a>Przykład

Ten przykład wywołuje **_get_tzname** , aby uzyskać wymagany rozmiar buforu, aby wyświetlić bieżącą nazwę czasu standardowego czasu letniego, przydziela bufor tego rozmiaru, wywołuje **_get_tzname** ponownie w celu załadowania nazwy w buforze, a następnie drukuje ją w konsoli programu.

```C
// crt_get_tzname.c
// Compile by using: cl /W4 crt_get_tzname.c
#include <stdio.h>
#include <time.h>
#include <malloc.h>

enum TZINDEX {
    STD,
    DST
};

int main()
{
    size_t tznameSize = 0;
    char * tznameBuffer = NULL;

    // Get the size of buffer required to hold DST time zone name
    if (_get_tzname(&tznameSize, NULL, 0, DST))
        return 1;    // Return an error value if it failed

    // Allocate a buffer for the name
    if (NULL == (tznameBuffer = (char *)(malloc(tznameSize))))
        return 2;    // Return an error value if it failed

    // Load the name in the buffer
    if (_get_tzname(&tznameSize, tznameBuffer, tznameSize, DST))
        return 3;    // Return an error value if it failed

    printf_s("The current Daylight standard time zone name is %s.\n", tznameBuffer);
    return 0;
}
```

### <a name="output"></a>Dane wyjściowe

```Output
The current Daylight standard time zone name is PDT.
```

## <a name="requirements"></a>Wymagania

|Procedura|Wymagany nagłówek|
|-------------|---------------------|
|**_get_tzname**|\<time.h>|

Aby uzyskać więcej informacji, zobacz [zgodność](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Zobacz też

[Zarządzanie czasem](../../c-runtime-library/time-management.md)<br/>
[errno, _doserrno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)<br/>
[_get_daylight](get-daylight.md)<br/>
[_get_dstbias](get-dstbias.md)<br/>
[_get_timezone](get-timezone.md)<br/>
