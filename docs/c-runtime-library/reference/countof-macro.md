---
title: _countof Macro | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
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
apitype: DLLExport
f1_keywords:
- _countof
- countof
dev_langs:
- C++
helpviewer_keywords:
- countof macro
- _countof macro
ms.assetid: 86198767-f7e5-4beb-898d-3cbbf60350a3
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1f83244ce231ff3e11bc6fee1bbd221840fc1b83
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/14/2018
---
# <a name="countof-macro"></a>_countof — Makro
Obliczanie liczby elementów w tablicy statycznie przydzielone.  
  
## <a name="syntax"></a>Składnia  
  
```  
size_t _countof(   
   array  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `array`  
 Nazwa tablicy.  
  
## <a name="return-value"></a>Wartość zwracana  
 Liczba elementów w tablicy, wyrażony jako `size_t`.  
  
## <a name="remarks"></a>Uwagi  
 Upewnij się, że `array` jest rzeczywiście tablicy, nie wskaźnik. W języku C `_countof` da błędne wyniki, jeśli `array` wskaźnik. W języku C++ `_countof` zakończy się niepowodzeniem do kompilacji Jeśli `array` wskaźnik.  
  
## <a name="requirements"></a>Wymagania  
  
|Macro|Wymagany nagłówek|  
|-----------|---------------------|  
|`_countof`|\<stdlib.h>|  
  
## <a name="example"></a>Przykład  
  
```  
// crt_countof.cpp  
#define _UNICODE  
#include <stdio.h>  
#include <stdlib.h>  
#include <tchar.h>  
  
int main( void )  
{  
   _TCHAR arr[20], *p;  
   printf( "sizeof(arr) = %zu bytes\n", sizeof(arr) );  
   printf( "_countof(arr) = %zu elements\n", _countof(arr) );  
   // In C++, the following line would generate a compile-time error:  
   // printf( "%zu\n", _countof(p) ); // error C2784 (because p is a pointer)  
  
   _tcscpy_s( arr, _countof(arr), _T("a string") );  
   // unlike sizeof, _countof works here for both narrow- and wide-character strings  
}  
```  
  
```Output  
sizeof(arr) = 40 bytes  
_countof(arr) = 20 elements  
```  
  
## <a name="see-also"></a>Zobacz też  
 [sizeof, operator](../../cpp/sizeof-operator.md)