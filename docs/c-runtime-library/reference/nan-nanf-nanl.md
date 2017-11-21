---
title: "nanf — NaN, nanl | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- nanf
- nan
- nanl
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
- api-ms-win-crt-math-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- nan
- nanl
- nanf
dev_langs: C++
helpviewer_keywords:
- nan function
- nanf function
- nanl function
ms.assetid: 790e9158-80ab-43e0-8f5a-096198553fd9
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 7e2b813f2e04871a29715c02a2635f741fb4e50b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/24/2017
---
# <a name="nan-nanf-nanl"></a>nan, nanf, nanl
Zwraca wartość quiet NaN.  
  
## <a name="syntax"></a>Składnia  
  
```  
double nan(  
   const char* input   
);  
float nanf(  
   const char* input   
);  
long double nanl(  
   const char* input   
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `input`  
 Wartość ciągu.  
  
## <a name="return-value"></a>Wartość zwracana  
 `nan` Zwracają quiet wartości NaN.  
  
## <a name="remarks"></a>Uwagi  
 `nan` Zwracają wartość zmiennoprzecinkowa, która odpowiada na NaN quiet (z systemem innym niż sygnalizacji). `input` Wartość jest ignorowana. Informacje, jak NaN są reprezentowane dla danych wyjściowych, zobacz [printf, _printf_l —, wprintf, _wprintf_l —](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md).  
  
## <a name="requirements"></a>Wymagania  
  
|Funkcja|Nagłówek C|Nagłówek C++|  
|--------------|--------------|------------------|  
|`nan`, `nanf`, `nanl`|\<Math.h >|\<cmath >|  
  
## <a name="see-also"></a>Zobacz też  
 [Obsługa liczb zmiennoprzecinkowych](../../c-runtime-library/floating-point-support.md)   
 [_finite —, _finitef](../../c-runtime-library/reference/finite-finitef.md)   
 [_fpclass, _fpclassf](../../c-runtime-library/reference/fpclass-fpclassf.md)   
 [isNaN _isnan —, _isnanf](../../c-runtime-library/reference/isnan-isnan-isnanf.md)