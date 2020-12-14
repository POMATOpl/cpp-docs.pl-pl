---
description: 'Dowiedz się więcej na temat: _fcvt'
title: _fcvt
ms.date: 4/2/2020
api_name:
- _fcvt
- _o__fcvt
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
- _fcvt
helpviewer_keywords:
- converting floating point, to strings
- _fcvt function
- floating-point functions, converting number to string
- fcvt function
- floating-point functions
ms.assetid: 74584c88-f0dd-4907-8fca-52da5df583f5
ms.openlocfilehash: 4d2439c586ec28526849e956b1302c444cafa3a4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97235765"
---
# <a name="_fcvt"></a>_fcvt

Konwertuje liczbę zmiennoprzecinkową na ciąg. Dostępna jest bezpieczniejsza wersja tej funkcji; Zobacz [_fcvt_s](fcvt-s.md).

## <a name="syntax"></a>Składnia

```C
char *_fcvt(
   double value,
   int count,
   int *dec,
   int *sign
);
```

### <a name="parameters"></a>Parametry

*wartość*<br/>
Liczba do przekonwertowania.

*liczbą*<br/>
Liczba cyfr po punkcie dziesiętnym.

*dec*<br/>
Wskaźnik do przechowywanej pozycji punktu dziesiętnego.

*sign*<br/>
Wskaźnik do przechowywanego wskaźnika podpisywania.

## <a name="return-value"></a>Wartość zwracana

**_fcvt** zwraca wskaźnik do ciągu cyfr, **null** w przypadku błędu.

## <a name="remarks"></a>Uwagi

Funkcja **_fcvt** konwertuje liczbę zmiennoprzecinkową na ciąg znaków zakończony znakiem null. Parametr *Value* jest liczbą zmiennoprzecinkową do przekonwertowania. **_fcvt** przechowuje cyfry *wartości* jako ciąg i dołącza znak null (' \ 0 '). Parametr *Count* określa liczbę cyfr, które mają być przechowywane po przecinku dziesiętnym. Nadmiarowe cyfry są zaokrąglane do *liczby* miejsc. W przypadku mniej niż *liczby* cyfr dokładności, ciąg jest dopełniany zerami.

Łączna liczba cyfr zwracanych przez **_fcvt** nie przekracza **_CVTBUFSIZE**.

W ciągu są przechowywane tylko cyfry. Pozycja punktu dziesiętnego i znak *wartości* można uzyskać od *gru* i podpisywać po wywołaniu. Parametr *gru* wskazuje na wartość całkowitą; Ta wartość całkowita wskazuje położenie punktu dziesiętnego w odniesieniu do początku ciągu. Wartość zero lub ujemna liczba całkowita wskazuje, że punkt dziesiętny znajduje się po lewej stronie pierwszej cyfry. *Znak* parametru wskazuje liczbę całkowitą wskazującą znak *wartości*. Liczba całkowita jest ustawiona na 0, jeśli *wartość* jest dodatnia i jest ustawiona *na wartość różną* od zera.

Różnica między **_ecvt** i **_fcvt** jest interpretowana parametru *Count* . **_ecvt** interpretuje *liczbę* jako łączną liczbę cyfr w ciągu danych wyjściowych, podczas gdy **_fcvt** interpretuje *licznik* jako liczbę cyfr po przecinku dziesiętnym.

**_ecvt** i **_fcvt** do konwersji Użyj jednego buforu przydzielenia statycznie. Każde wywołanie jednej z tych procedur niszczy wyniki poprzedniego wywołania.

Ta funkcja sprawdza poprawność swoich parametrów. Jeśli *gru* lub *Sign* ma **wartość null** lub *licznik* ma wartość 0, zostanie wywołana procedura obsługi nieprawidłowego parametru, zgodnie z opisem w [walidacji parametru](../../c-runtime-library/parameter-validation.md). Jeśli wykonanie może być kontynuowane, **errno** jest ustawiona na **EINVAL** i zwracana jest **wartość null** .

Domyślnie globalny stan tej funkcji jest objęty zakresem aplikacji. Aby to zmienić, zobacz [stan globalny w CRT](../global-state.md).

## <a name="requirements"></a>Wymagania

|Funkcja|Wymagany nagłówek|
|--------------|---------------------|
|**_fcvt**|\<stdlib.h>|

Aby uzyskać więcej informacji o zgodności, zobacz [zgodność](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Przykład

```C
// crt_fcvt.c
// compile with: /W3
// This program converts the constant
// 3.1415926535 to a string and sets the pointer
// buffer to point to that string.

#include <stdlib.h>
#include <stdio.h>

int main( void )
{
   int  decimal, sign;
   char *buffer;
   double source = 3.1415926535;

   buffer = _fcvt( source, 7, &decimal, &sign ); // C4996
   // Note: _fcvt is deprecated; consider using _fcvt_s instead
   printf( "source: %2.10f   buffer: '%s'   decimal: %d   sign: %d\n",
            source, buffer, decimal, sign );
}
```

```Output
source: 3.1415926535   buffer: '31415927'   decimal: 1   sign: 0
```

## <a name="see-also"></a>Zobacz także

[Konwersja danych](../../c-runtime-library/data-conversion.md)<br/>
[Obsługa zmiennoprzecinkowa](../../c-runtime-library/floating-point-support.md)<br/>
[atof, _atof_l, _wtof, _wtof_l](atof-atof-l-wtof-wtof-l.md)<br/>
[_ecvt](ecvt.md)<br/>
[_gcvt](gcvt.md)<br/>
