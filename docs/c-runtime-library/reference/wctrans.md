---
title: wctrans
ms.date: 11/04/2016
apiname:
- wctrans
apilocation:
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
apitype: DLLExport
f1_keywords:
- wctrans
helpviewer_keywords:
- character codes, wctrans
- characters, codes
- characters, converting
- wctrans function
ms.assetid: 215404bf-6d60-489c-9ae9-880e6b586162
ms.openlocfilehash: 3c7aace7a93160d2e9a4c1523d49bcaf6ae4dc20
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/23/2019
ms.locfileid: "62188458"
---
# <a name="wctrans"></a>wctrans

Określa mapowania z jednego zestawu kodów znaków do innego.

## <a name="syntax"></a>Składnia

```C
wctrans_t wctrans(
   const char *property
);
```

### <a name="parameters"></a>Parametry

*właściwość*<br/>
Ciąg, który określa jedno z prawidłową przekształcenia.

## <a name="return-value"></a>Wartość zwracana

Jeśli **LC_CTYPE** kategorii bieżących ustawień regionalnych nie definiuje mapowania, których nazwa pasuje do ciągu właściwość *właściwość*, funkcja zwraca wartość zero. W przeciwnym razie zwraca wartość różną od zera odpowiedni do użytku jako drugi argument na kolejne wywołanie [towctrans —](towctrans.md).

## <a name="remarks"></a>Uwagi

Ta funkcja określa mapowania z jednego zestawu kodów znaków do innego.

Następujące pary wywołania mają takie samo zachowanie we wszystkich ustawieniach regionalnych, ale można zdefiniować dodatkowe mapowania nawet w przypadku ustawień regionalnych "C":

|Funkcja|Takie same jak|
|--------------|-------------|
|tolower(c)|towctrans — (c, wctrans("towlower"))|
|towupper(c)|towctrans — (c, wctrans("toupper"))|

## <a name="requirements"></a>Wymagania

|Procedura|Wymagany nagłówek|
|-------------|---------------------|
|**wctrans**|\<wctype.h>|

Aby uzyskać dodatkowe informacje o zgodności, zobacz [zgodności](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Przykład

```C
// crt_wctrans.cpp
// compile with: /EHsc
// This example determines a mapping from one set of character
// codes to another.

#include <wchar.h>
#include <wctype.h>
#include <stdio.h>
#include <iostream>

int main()
{
    wint_t c = 'a';
    printf_s("%d\n",c);

    wctrans_t i = wctrans("toupper");
    printf_s("%d\n",i);

    wctrans_t ii = wctrans("towlower");
    printf_s("%d\n",ii);

    wchar_t wc = towctrans(c, i);
    printf_s("%d\n",wc);
}
```

```Output
97
1
0
65
```

## <a name="see-also"></a>Zobacz także

[Konwersja danych](../../c-runtime-library/data-conversion.md)<br/>
[setlocale, _wsetlocale](setlocale-wsetlocale.md)<br/>
