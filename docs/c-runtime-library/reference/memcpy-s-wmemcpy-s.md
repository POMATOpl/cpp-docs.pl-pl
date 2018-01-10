---
title: "memcpy_s —, wmemcpy_s — | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- memcpy_s
- wmemcpy_s
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
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- wmemcpy_s
- memcpy_s
dev_langs: C++
helpviewer_keywords:
- memcpy_s function
- wmemcpy_s function
ms.assetid: 5504e20a-83d9-4063-91fc-3f55f7dabe99
caps.latest.revision: "27"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5748077731b07a0deeb4e601221b0ba412be391f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/21/2017
---
# <a name="memcpys-wmemcpys"></a>memcpy_s, wmemcpy_s
Kopie bajty pomiędzy buforów. Są to wersje [memcpy, wmemcpy —](../../c-runtime-library/reference/memcpy-wmemcpy.md) ulepszeń zabezpieczeń zgodnie z opisem w [funkcje zabezpieczeń w CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## <a name="syntax"></a>Składnia  
  
```  
errno_t memcpy_s(  
   void *dest,  
   size_t destSize,  
   const void *src,  
   size_t count   
);  
errno_t wmemcpy_s(  
   wchar_t *dest,  
   size_t destSize,  
   const wchar_t *src,  
   size_t count  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `dest`  
 Bufor nowego.  
  
 `destSize`  
 Rozmiar buforu docelowego dla memcpy_s — i znaki dwubajtowe (wchar_t) dla wmemcpy_s — wyrażony w bajtach.  
  
 `src`  
 Bufor do skopiowania.  
  
 `count`  
 Liczba znaków do skopiowania.  
  
## <a name="return-value"></a>Wartość zwracana  
 Zero w przypadku powodzenia; błąd o kodzie błędu.  
  
### <a name="error-conditions"></a>Warunki błędów  
  
|`dest`|`destSize`|`src`|`count`|Wartość zwracana|Zawartość`dest`|  
|------------|----------------|-----------|---|------------------|------------------------|  
|wszystkie|wszystkie|wszystkie|0|0|Nie zmodyfikowano|  
|`NULL`|wszystkie|wszystkie|inną niż zero|`EINVAL`|Nie zmodyfikowano|  
|wszystkie|wszystkie|`NULL`|inną niż zero|`EINVAL`|`dest`powoduje|  
|wszystkie|< `count`|wszystkie|inną niż zero|`ERANGE`|`dest`powoduje|  
  
## <a name="remarks"></a>Uwagi  
 `memcpy_s`kopie `count` bajtów z `src` do `dest`; `wmemcpy_s` kopie `count` znaki dwubajtowe (dwa bajty). Jeśli na źródłowym i docelowym nakładają się, zachowanie `memcpy_s` jest niezdefiniowana. Użyj `memmove_s` do obsługi pokrywających się obszarów.  
  
 Te funkcje walidację ich parametrów. Jeśli `count` jest różna od zera i `dest` lub `src` jest wskaźnika o wartości null, lub `destSize` jest mniejszy niż `count`, te funkcje Wywołaj program obsługi nieprawidłowych parametrów, zgodnie z opisem w [sprawdzanie poprawności parametru](../../c-runtime-library/parameter-validation.md). Jeśli jest dozwolone wykonywanie, aby kontynuować, te funkcje zwracają `EINVAL` lub `ERANGE` i ustaw `errno` do wartości zwracanej.  
  
## <a name="requirements"></a>Wymagania  
  
|Procedura|Wymagany nagłówek|  
|-------------|---------------------|  
|`memcpy_s`|\<Memory.h > lub \<string.h >|  
|`wmemcpy_s`|\<WChar.h >|  
  
 Aby uzyskać dodatkowe informacje o zgodności, zobacz [zgodności](../../c-runtime-library/compatibility.md) we wprowadzeniu.  
  
## <a name="example"></a>Przykład  
  
```  
// crt_memcpy_s.c  
// Copy memory in a more secure way.  
  
#include <memory.h>  
#include <stdio.h>  
  
int main()  
{  
   int a1[10], a2[100], i;  
   errno_t err;  
  
   // Populate a2 with squares of integers  
   for (i = 0; i < 100; i++)  
   {  
      a2[i] = i*i;  
   }  
  
   // Tell memcpy_s to copy 10 ints (40 bytes), giving  
   // the size of the a1 array (also 40 bytes).  
   err = memcpy_s(a1, sizeof(a1), a2, 10 * sizeof (int) );      
   if (err)  
   {  
      printf("Error executing memcpy_s.\n");  
   }  
   else  
   {  
     for (i = 0; i < 10; i++)  
       printf("%d ", a1[i]);  
   }  
   printf("\n");  
}  
```  
  
```Output  
0 1 4 9 16 25 36 49 64 81   
```  
  
## <a name="see-also"></a>Zobacz też  
 [Manipulowanie buforem](../../c-runtime-library/buffer-manipulation.md)   
 [_memccpy —](../../c-runtime-library/reference/memccpy.md)   
 [memchr, wmemchr —](../../c-runtime-library/reference/memchr-wmemchr.md)   
 [funkcji memcmp, wmemcmp —](../../c-runtime-library/reference/memcmp-wmemcmp.md)   
 [memmove —, wmemmove —](../../c-runtime-library/reference/memmove-wmemmove.md)   
 [memset —, wmemset —](../../c-runtime-library/reference/memset-wmemset.md)   
 [strcpy wcscpy —, _mbscpy —](../../c-runtime-library/reference/strcpy-wcscpy-mbscpy.md)   
 [strncpy —, _strncpy_l —, wcsncpy —, _wcsncpy_l — _mbsncpy —, _mbsncpy_l —](../../c-runtime-library/reference/strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)   
 [strncpy_s, _strncpy_s_l, wcsncpy_s, _wcsncpy_s_l, _mbsncpy_s, _mbsncpy_s_l](../../c-runtime-library/reference/strncpy-s-strncpy-s-l-wcsncpy-s-wcsncpy-s-l-mbsncpy-s-mbsncpy-s-l.md)