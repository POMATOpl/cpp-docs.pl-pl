---
title: "_itoa_s —, _i64toa_s —, _ui64toa_s —, _itow_s —, _i64tow_s —, _ui64tow_s — | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _ui64tow_s
- _itoa_s
- _itow_s
- _ui64toa_s
- _i64tow_s
- _i64toa_s
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
- i64tot_s
- itow_s
- _ui64tow_s
- _itow_s
- ui64tot_s
- _ui64toa_s
- itoa_s
- _i64tow_s
- _i64tot_s
- _itot_s
- _i64toa_s
- _itoa_s
- ui64toa_s
- i64toa_s
- _ui64tot_s
- i64tow_s
- itot_s
dev_langs: C++
helpviewer_keywords:
- _ui64toa_s function
- _itow_s function
- _i64tow_s function
- _itot_s function
- converting integers
- itow_s function
- i64toa_s function
- _ui64tow_s function
- integers, converting
- _i64tot_s function
- itoa_s function
- _itoa_s function
- ui64toa_s function
- i64tow_s function
- converting numbers, to strings
- _ui64tot_s function
- _i64toa_s function
ms.assetid: eb746581-bff3-48b5-a973-bfc0a4478ecf
caps.latest.revision: "28"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1499f3feb76219ac03362fef70e4c3b516a8f060
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/21/2017
---
# <a name="itoas-i64toas-ui64toas-itows-i64tows-ui64tows"></a>_itoa_s, _i64toa_s, _ui64toa_s, _itow_s, _i64tow_s, _ui64tow_s
Konwertuje liczbę całkowitą na ciąg. Są to wersje [_itoa —, _i64toa —, _ui64toa —, _itow —, _i64tow —, _ui64tow —](../../c-runtime-library/reference/itoa-i64toa-ui64toa-itow-i64tow-ui64tow.md) ulepszeń zabezpieczeń zgodnie z opisem w [funkcje zabezpieczeń w CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## <a name="syntax"></a>Składnia  
  
```  
errno_t _itoa_s(  
   int value,  
   char *buffer,  
   size_t sizeInCharacters,  
   int radix   
);  
errno_t _i64toa_s(  
   __int64 value,  
   char *buffer,  
   size_t sizeInCharacters,  
   int radix   
);  
errno_t _ui64toa_s(  
   unsigned _int64 value,  
   char *buffer,  
   size_t sizeInCharacters,  
   int radix   
);  
errno_t _itow_s(  
   int value,  
   wchar_t *buffer,  
   size_t sizeInCharacters,  
   int radix   
);  
errno_t _i64tow_s(  
   __int64 value,  
   wchar_t *buffer,  
   size_t sizeInCharacters,  
   int radix   
);  
errno_t _ui64tow_s(  
   unsigned __int64 value,  
   wchar_t *buffer,  
   size_t sizeInCharacters,  
   int radix   
);  
template <size_t size>  
errno_t _itoa_s(  
   int value,  
   char (&buffer)[size],  
   int radix   
); // C++ only  
template <size_t size>  
errno_t _itow_s(  
   int value,  
   wchar_t (&buffer)[size],  
   int radix   
); // C++ only  
```  
  
#### <a name="parameters"></a>Parametry  
 [in]`value`  
 Numer do skonwertowania.  
  
 [out]`buffer`  
 Wypełniony wynik konwersji.  
  
 [in]`sizeInCharacters`  
 Rozmiar buforu w znaki jednobajtowe lub znaki dwubajtowe.  
  
 [in]`radix`  
 Podstawa `value`; którego musi należeć do zakresu 2 36.  
  
## <a name="return-value"></a>Wartość zwracana  
 Zero w przypadku powodzenia; błąd o kodzie błędu. Jeśli dowolny z następujących warunków ma zastosowanie funkcja wywołuje program obsługi nieprawidłowych parametrów, zgodnie z opisem w [sprawdzanie poprawności parametru](../../c-runtime-library/parameter-validation.md).  
  
### <a name="error-conditions"></a>Warunki błędów  
  
|value|Bufor|sizeInCharacters|Podstawa|Zwraca|  
|-----------|------------|----------------------|-----------|------------|  
|wszystkie|`NULL`|wszystkie|wszystkie|`EINVAL`|  
|wszystkie|wszystkie|<=0|wszystkie|`EINVAL`|  
|wszystkie|wszystkie|< = długość ciągu wynik wymagane|wszystkie|`EINVAL`|  
|wszystkie|wszystkie|wszystkie|`radix`< 2 lub `radix` > 36|`EINVAL`|  
  
 **Problemy dotyczące zabezpieczeń**  
  
 Funkcje te mogą generować naruszenia zasad dostępu, jeśli `buffer` nie wskazuje na prawidłową pamięci i nie jest `NULL`, lub jeśli długość buforu nie jest wystarczająco długi pomieścić ciąg wyniku.  
  
## <a name="remarks"></a>Uwagi  
 Z wyjątkiem tych parametrów i zwracanych wartości `_itoa_s` funkcje mają takie samo zachowanie jako odpowiednie mniej bezpieczny wersji.  
  
 W języku C++ za pomocą tych funkcji zostało uproszczone dzięki przeciążenia szablonu; przeciążeń można automatycznie rozpoznać długość buforu (wyeliminowanie konieczności określania argumentem rozmiaru) i automatycznie można zastąpić starszą, które nie są bezpieczne funkcje z ich odpowiedniki nowsza, bezpieczne. Aby uzyskać więcej informacji, zobacz [Secure szablonu Overloads](../../c-runtime-library/secure-template-overloads.md).  
  
 Wersje tych funkcji do debugowania najpierw wprowadzić bufor 0xFD. Aby wyłączyć to zachowanie, użyj [_crtsetdebugfillthreshold —](../../c-runtime-library/reference/crtsetdebugfillthreshold.md).  
  
### <a name="generic-text-routine-mappings"></a>Mapowania procedur zwykłego tekstu  
  
|Procedura tchar.h|_UNICODE i _MBCS niezdefiniowane|_MBCS zdefiniowano|_UNICODE zdefiniowano|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_itot_s`|`_itoa_s`|`_itoa_s`|`_itow_s`|  
|`_i64tot_s`|`_i64toa_s`|`_i64toa_s`|`_i64tow_s`|  
|`_ui64tot_s`|`_ui64toa_s`|`_ui64toa_s`|`_ui64tow_s`|  
  
## <a name="requirements"></a>Wymagania  
  
|Procedura|Wymagany nagłówek|  
|-------------|---------------------|  
|`_itoa_s`|\<stdlib.h >|  
|`_i64toa_s`|\<stdlib.h >|  
|`_ui64toa_s`|\<stdlib.h >|  
|`_itow_s`|\<stdlib.h > lub \<wchar.h >|  
|`_i64tow_s`|\<stdlib.h > lub \<wchar.h >|  
|`_ui64tow_s`|\<stdlib.h > lub \<wchar.h >|  
  
 Aby uzyskać więcej informacji o zgodności, zobacz [zgodności](../../c-runtime-library/compatibility.md) we wprowadzeniu.  
  
## <a name="example"></a>Przykład  
  
```  
// crt_itoa_s.c  
#include <stdlib.h>  
#include <string.h>  
  
int main( void )  
{  
    char buffer[65];  
    int r;  
    for( r=10; r>=2; --r )  
    {  
       _itoa_s( -1, buffer, 65, r );  
       printf( "base %d: %s (%d chars)\n", r, buffer, strnlen(buffer, _countof(buffer)) );  
    }  
    printf( "\n" );  
    for( r=10; r>=2; --r )  
    {  
       _i64toa_s( -1L, buffer, 65, r );  
       printf( "base %d: %s (%d chars)\n", r, buffer, strnlen(buffer, _countof(buffer)) );  
    }  
    printf( "\n" );  
    for( r=10; r>=2; --r )  
    {  
       _ui64toa_s( 0xffffffffffffffffL, buffer, 65, r );  
       printf( "base %d: %s (%d chars)\n", r, buffer, strnlen(buffer, _countof(buffer)) );  
    }  
}  
```  
  
## <a name="output"></a>Dane wyjściowe  
  
```  
base 10: -1 (2 chars)  
base 9: 12068657453 (11 chars)  
base 8: 37777777777 (11 chars)  
base 7: 211301422353 (12 chars)  
base 6: 1550104015503 (13 chars)  
base 5: 32244002423140 (14 chars)  
base 4: 3333333333333333 (16 chars)  
base 3: 102002022201221111210 (21 chars)  
base 2: 11111111111111111111111111111111 (32 chars)  
  
base 10: -1 (2 chars)  
base 9: 145808576354216723756 (21 chars)  
base 8: 1777777777777777777777 (22 chars)  
base 7: 45012021522523134134601 (23 chars)  
base 6: 3520522010102100444244423 (25 chars)  
base 5: 2214220303114400424121122430 (28 chars)  
base 4: 33333333333333333333333333333333 (32 chars)  
base 3: 11112220022122120101211020120210210211220 (41 chars)  
base 2: 1111111111111111111111111111111111111111111111111111111111111111 (64 chars)  
  
base 10: 18446744073709551615 (20 chars)  
base 9: 145808576354216723756 (21 chars)  
base 8: 1777777777777777777777 (22 chars)  
base 7: 45012021522523134134601 (23 chars)  
base 6: 3520522010102100444244423 (25 chars)  
base 5: 2214220303114400424121122430 (28 chars)  
base 4: 33333333333333333333333333333333 (32 chars)  
base 3: 11112220022122120101211020120210210211220 (41 chars)  
base 2: 1111111111111111111111111111111111111111111111111111111111111111 (64 chars)  
```  
  
## <a name="see-also"></a>Zobacz też  
 [Konwersja danych](../../c-runtime-library/data-conversion.md)   
 [_ltoa —, _ltow —](../../c-runtime-library/reference/ltoa-ltow.md)   
 [_ultoa, _ultow](../../c-runtime-library/reference/ultoa-ultow.md)