---
title: "ctime —, _ctime32 —, _ctime64 —, _wctime —, _wctime32 —, _wctime64 — | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _ctime64
- _wctime32
- ctime
- _wctime64
- _ctime32
- _wctime
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
- api-ms-win-crt-time-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _wctime64
- _ctime32
- _tctime
- _wctime
- _wctime32
- _tctime64
- _ctime64
- ctime
dev_langs: C++
helpviewer_keywords:
- tctime64 function
- _ctime32 function
- ctime32 function
- _wctime function
- wctime64 function
- _tctime64 function
- _tctime32 function
- _ctime64 function
- _wctime64 function
- ctime function
- wctime32 function
- ctime64 function
- _wctime32 function
- _tctime function
- tctime32 function
- tctime function
- wctime function
- time, converting
ms.assetid: 2423de37-a35c-4f0a-a378-3116bc120a9d
caps.latest.revision: "25"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 97c6f5f4c827ca315eb1de36ee8d4f19d94214bd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/21/2017
---
# <a name="ctime-ctime32-ctime64-wctime-wctime32-wctime64"></a>ctime, _ctime32, _ctime64, _wctime, _wctime32, _wctime64
Wartość czasu jest skonwertowana do ciągu oraz dostosować ustawienia strefy czasu lokalnego. Bezpieczniejsza wersje te funkcje są dostępne; zobacz [ctime_s —, _ctime32_s —, _ctime64_s —, _wctime_s —, _wctime32_s —, _wctime64_s —](../../c-runtime-library/reference/ctime-s-ctime32-s-ctime64-s-wctime-s-wctime32-s-wctime64-s.md).  
  
## <a name="syntax"></a>Składnia  
  
```  
char *ctime(   
   const time_t *timer   
);  
char *_ctime32(   
   const __time32_t *timer )  
;  
char *_ctime64(   
   const __time64_t *timer )  
;  
wchar_t *_wctime(   
   const time_t *timer   
);  
wchar_t *_wctime32(   
   const __time32_t *timer  
);  
wchar_t *_wctime64(   
   const __time64_t *timer   
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `timer`  
 Wskaźnik do czasu przechowywane.  
  
## <a name="return-value"></a>Wartość zwracana  
 Wskaźnik do wyniku ciąg znaków. `NULL`zostanie zwrócony, jeśli:  
  
-   `time`reprezentuje datę przed północy, 1 stycznia 1970 UTC.  
  
-   Jeśli używasz `_ctime32` lub `_wctime32` i `time` reprezentuje datę wypadającą po 23:59:59 18 stycznia 2038 r., UTC.  
  
-   Jeśli używasz `_ctime64` lub `_wctime64` i `time` reprezentuje datę wypadającą po 23:59:59 31 grudnia 3000 UTC.  
  
 `ctime`jest wbudowaną funkcją, która daje w wyniku `_ctime64` i `time_t` jest odpowiednikiem `__time64_t`. Aby wymusić kompilatora, aby zinterpretować `time_t` jako starego 32-bitowych `time_t`, można zdefiniować `_USE_32BIT_TIME_T`. To spowoduje `ctime` mogła zwrócić `_ctime32`. Nie jest to zalecane, ponieważ aplikacja może zakończyć się niepowodzeniem po 18 stycznia 2038 r., a nie jest dozwolona na platformach 64-bitowych.  
  
## <a name="remarks"></a>Uwagi  
 `ctime` Funkcja konwertuje przechowywanych jako wartość czasu [time_t —](../../c-runtime-library/standard-types.md) wartość na ciąg znaków. `timer` Wartość zazwyczaj jest uzyskiwana w wyniku wywołania [czas](../../c-runtime-library/reference/time-time32-time64.md), która zwraca liczbę sekund, jaka upłynęła od północy (00: 00:00), 1 stycznia 1970, uniwersalny czas koordynowany (UTC). Zwracana wartość ciągu zawiera dokładnie 26 znaków i ma postać:  
  
```  
Wed Jan 02 02:03:55 1980\n\0  
```  
  
 24-godzinnym jest używany. Wszystkie pola mają stałej szerokości. Znak nowego wiersza ("\n") i znak null ('\0') zajmują ostatnich dwóch pozycji w ciągu.  
  
 Ciąg przekonwertowany znaków jest również dostosowywana zgodnie z ustawieniami strefy czasu lokalnego. Zobacz `time`, [_ftime —](../../c-runtime-library/reference/ftime-ftime32-ftime64.md), i [konwersję](../../c-runtime-library/reference/localtime-localtime32-localtime64.md) funkcji, aby uzyskać informacje na temat konfigurowania lokalnego czasu i [_tzset —](../../c-runtime-library/reference/tzset.md) szczegółowe informacje na temat definiowania — funkcja Strefa czasowa środowiska i zmiennych globalnych.  
  
 Wywołanie `ctime` modyfikuje pojedynczy bufor przydzielony statycznie używane przez `gmtime` i `localtime` funkcji. Każde wywołanie do jednej z tych procedur niszczy wynik poprzedniego wywołania. `ctime`udostępnia statyczny buforu z `asctime` funkcji. W związku z tym wywołaniu `ctime` niszczy wyniki wszelkie poprzednie wywołanie `asctime`, `localtime`, lub `gmtime`.  
  
 `_wctime`i `_wctime64` są wersja znaków dwubajtowych `ctime` i `_ctime64`; zwracającej wskaźnik na ciąg znaków dwubajtowych. W przeciwnym razie `_ctime64`, `_wctime`, i `_wctime64` zachowują się tak samo do `ctime`.  
  
 Te funkcje walidację ich parametrów. Jeśli `timer` jest wskaźnika o wartości null, lub jeśli wartość czasomierza jest ujemna, te funkcje wywołanie program obsługi nieprawidłowych parametrów, zgodnie z opisem w [sprawdzanie poprawności parametru](../../c-runtime-library/parameter-validation.md). Jeśli jest dozwolone wykonywanie, aby kontynuować, funkcje zwracają `NULL` i ustaw `errno` do `EINVAL`.  
  
### <a name="generic-text-routine-mappings"></a>Mapowania procedur zwykłego tekstu  
  
|Procedura TCHAR.H|_Unicode — & _MBCS nie zdefiniowany|_MBCS zdefiniowano|_UNICODE zdefiniowano|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tctime`|`ctime`|`ctime`|`_wctime`|  
|`_tctime32`|`_ctime32`|`_ctime32`|`_wctime32`|  
|`_tctime64`|`_ctime64`|`_ctime64`|`_wctime64`|  
  
## <a name="requirements"></a>Wymagania  
  
|Procedura|Wymagany nagłówek|  
|-------------|---------------------|  
|`ctime`|\<Time.h >|  
|`_ctime32`|\<Time.h >|  
|`_ctime64`|\<Time.h >|  
|`_wctime`|\<Time.h > lub \<wchar.h >|  
|`_wctime32`|\<Time.h > lub \<wchar.h >|  
|`_wctime64`|\<Time.h > lub \<wchar.h >|  
  
 Aby uzyskać dodatkowe informacje o zgodności, zobacz [zgodności](../../c-runtime-library/compatibility.md) we wprowadzeniu.  
  
## <a name="example"></a>Przykład  
  
```  
// crt_ctime64.c  
// compile with: /W3  
/* This program gets the current  
 * time in _time64_t form, then uses ctime to  
 * display the time in string form.  
 */  
  
#include <time.h>  
#include <stdio.h>  
  
int main( void )  
{  
   __time64_t ltime;  
  
   _time64( &ltime );  
   printf( "The time is %s\n", _ctime64( &ltime ) ); // C4996  
   // Note: _ctime64 is deprecated; consider using _ctime64_s  
}  
```  
  
```Output  
The time is Wed Feb 13 16:04:43 2002  
```  
  
## <a name="see-also"></a>Zobacz też  
 [Zarządzanie czasem](../../c-runtime-library/time-management.md)   
 [asctime —, _wasctime —](../../c-runtime-library/reference/asctime-wasctime.md)   
 [ctime_s —, _ctime32_s —, _ctime64_s —, _wctime_s — _wctime32_s —, _wctime64_s —](../../c-runtime-library/reference/ctime-s-ctime32-s-ctime64-s-wctime-s-wctime32-s-wctime64-s.md)   
 [_ftime —, _ftime32 —, _ftime64 —](../../c-runtime-library/reference/ftime-ftime32-ftime64.md)   
 [gmtime —, _gmtime32 —, _gmtime64 —](../../c-runtime-library/reference/gmtime-gmtime32-gmtime64.md)   
 [czas lokalny, _localtime32 —, _localtime64 —](../../c-runtime-library/reference/localtime-localtime32-localtime64.md)   
 [time, _time32, _time64](../../c-runtime-library/reference/time-time32-time64.md)