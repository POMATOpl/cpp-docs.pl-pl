---
title: _getmaxstdio | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _getmaxstdio
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _getmaxstdio
- getmaxstdio
dev_langs:
- C++
helpviewer_keywords:
- files [C++], number open
- _getmaxstdio function
- getmaxstdio function
- open files, getting number
ms.assetid: 700ca8ce-4a8c-4e00-9467-dfa9d6b831a0
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 89a7e989406e5726d0ad5a2a42eaa2198dee6b72
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/14/2018
---
# <a name="getmaxstdio"></a>_getmaxstdio
Zwraca liczbę równocześnie otwarte pliki w poziomie we/wy strumienia.  
  
## <a name="syntax"></a>Składnia  
  
```  
int _getmaxstdio( void );  
```  
  
## <a name="return-value"></a>Wartość zwracana  
 Zwraca liczbę reprezentującą liczbę jednocześnie otwartych plików, w obecnie dozwolone `stdio` poziom.  
  
## <a name="remarks"></a>Uwagi  
 Użyj [_setmaxstdio —](../../c-runtime-library/reference/setmaxstdio.md) Aby skonfigurować liczbę równocześnie otwarte pliki w `stdio` poziom.  
  
## <a name="requirements"></a>Wymagania  
  
|Procedura|Wymagany nagłówek|  
|-------------|---------------------|  
|`_getmaxstdio`|\<stdio.h>|  
  
 Aby uzyskać więcej informacji o zgodności, zobacz [zgodności](../../c-runtime-library/compatibility.md) we wprowadzeniu.  
  
## <a name="example"></a>Przykład  
  
```  
// crt_setmaxstdio.c  
// The program retrieves the maximum number  
// of open files and prints the results  
// to the console.  
  
#include <stdio.h>  
  
int main()  
{  
   printf( "%d\n", _getmaxstdio());  
  
   _setmaxstdio(2048);  
  
   printf( "%d\n", _getmaxstdio());  
}  
```  
  
```Output  
512  
2048  
```  
  
## <a name="see-also"></a>Zobacz też  
 [We/Wy strumienia](../../c-runtime-library/stream-i-o.md)