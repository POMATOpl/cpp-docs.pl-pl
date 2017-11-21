---
title: "_TRUNCATE — | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _TRUNCATE
- TRUNCATE
dev_langs: C++
helpviewer_keywords:
- TRUNCATE constant
- _TRUNCATE constant
ms.assetid: ad093dbf-1aa5-4bd2-9268-efc68afd8434
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 2f34ae91dc57675e01859842a6e23a65f41520c2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/24/2017
---
# <a name="truncate"></a>_TRUNCATE
Określa zachowanie obcięcie ciągu.  
  
## <a name="syntax"></a>Składnia  
  
```  
#include <stdlib.h>  
```  
  
## <a name="remarks"></a>Uwagi  
 `_TRUNCATE`Włącza zachowanie obcięcie, gdy dane są przekazywane jako `count` parametru do tych funkcji:  
  
 [strncpy_s — _strncpy_s_l —, wcsncpy_s —, _wcsncpy_s_l —, _mbsncpy_s, _mbsncpy_s_l](../c-runtime-library/reference/strncpy-s-strncpy-s-l-wcsncpy-s-wcsncpy-s-l-mbsncpy-s-mbsncpy-s-l.md)  
  
 [strncat_s —, _strncat_s_l, wcsncat_s —, _wcsncat_s_l _mbsncat_s —, _mbsncat_s_l —](../c-runtime-library/reference/strncat-s-strncat-s-l-wcsncat-s-wcsncat-s-l-mbsncat-s-mbsncat-s-l.md)  
  
 [mbstowcs_s —, _mbstowcs_s_l —](../c-runtime-library/reference/mbstowcs-s-mbstowcs-s-l.md)  
  
 [mbsrtowcs_s —](../c-runtime-library/reference/mbsrtowcs-s.md)  
  
 [wcstombs_s —, _wcstombs_s_l —](../c-runtime-library/reference/wcstombs-s-wcstombs-s-l.md)  
  
 [wcsrtombs_s —](../c-runtime-library/reference/wcsrtombs-s.md)  
  
 [_snprintf_s —, _snprintf_s_l —, _snwprintf_s — _snwprintf_s_l —](../c-runtime-library/reference/snprintf-s-snprintf-s-l-snwprintf-s-snwprintf-s-l.md)  
  
 [vsnprintf_s — _vsnprintf_s —, _vsnprintf_s_l —, _vsnwprintf_s —, _vsnwprintf_s_l —](../c-runtime-library/reference/vsnprintf-s-vsnprintf-s-vsnprintf-s-l-vsnwprintf-s-vsnwprintf-s-l.md)  
  
 Jeśli bufor docelowy jest zbyt mały, aby pomieścić cały ciąg, normalne działanie tych funkcji jest traktowany jako błąd (zobacz [sprawdzanie poprawności parametru](../c-runtime-library/parameter-validation.md)). Jednak włączenie obcięcie ciągu przez przekazanie `_TRUNCATE`, te funkcje będą kopiowane tylko znacznie ciągu, ile zmieści, pozostawiając bufor docelowy zerem i zwróć pomyślnie.  
  
 Obcięcie ciągu zmiany wartości zwracanych odpowiednich funkcji. Następujące funkcje zwraca 0, jeśli nie zostanie obcięte, lub `STRUNCATE` ewentualnych obcięcie:  
  
 [strncpy_s — _strncpy_s_l —, wcsncpy_s —, _wcsncpy_s_l —, _mbsncpy_s, _mbsncpy_s_l](../c-runtime-library/reference/strncpy-s-strncpy-s-l-wcsncpy-s-wcsncpy-s-l-mbsncpy-s-mbsncpy-s-l.md)  
  
 [strncat_s —, _strncat_s_l, wcsncat_s —, _wcsncat_s_l _mbsncat_s —, _mbsncat_s_l —](../c-runtime-library/reference/strncat-s-strncat-s-l-wcsncat-s-wcsncat-s-l-mbsncat-s-mbsncat-s-l.md)  
  
 [wcstombs_s —, _wcstombs_s_l —](../c-runtime-library/reference/wcstombs-s-wcstombs-s-l.md)  
  
 [mbstowcs_s —, _mbstowcs_s_l —](../c-runtime-library/reference/mbstowcs-s-mbstowcs-s-l.md)  
  
 Następujące funkcje zwraca liczbę znaków, jeśli nie zostanie obcięte kopiowany lub wartość -1 ewentualnych obcięcie (dopasowanie zachowanie funkcji snprintf — oryginalny):  
  
 [_snprintf_s —, _snprintf_s_l —, _snwprintf_s — _snwprintf_s_l —](../c-runtime-library/reference/snprintf-s-snprintf-s-l-snwprintf-s-snwprintf-s-l.md)  
  
 [vsnprintf_s — _vsnprintf_s —, _vsnprintf_s_l —, _vsnwprintf_s —, _vsnwprintf_s_l —](../c-runtime-library/reference/vsnprintf-s-vsnprintf-s-vsnprintf-s-l-vsnwprintf-s-vsnwprintf-s-l.md)  
  
## <a name="example"></a>Przykład  
  
```  
// crt_truncate.c  
#include <stdlib.h>  
#include <errno.h>  
  
int main()  
{  
   char src[] = "1234567890";  
   char dst[5];  
   errno_t err = strncpy_s(dst, _countof(dst), src, _TRUNCATE);  
   if ( err == STRUNCATE )  
      printf( "truncation occurred!\n" );  
   printf( "'%s'\n", dst );  
}  
```  
  
```Output  
truncation occurred!  
'1234'  
```  
  
## <a name="see-also"></a>Zobacz też  
 [Stałe globalne](../c-runtime-library/global-constants.md)