---
title: "_chgsign —, _chgsignf —, _chgsignl — | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _chgsignl
- _chgsign
- _chgsignf
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
- _chgsignf
- chgsign
- _chgsignl
- _chgsign
dev_langs: C++
helpviewer_keywords:
- _chgsignl function
- _chgsignf function
- chgsign function
- _chgsign function
ms.assetid: a6646f8e-213d-4564-8617-f43bc66f989f
caps.latest.revision: "17"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 2091576b5792fb2b7e064eec7db71fabea146563
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/24/2017
---
# <a name="chgsign-chgsignf-chgsignl"></a>_chgsign, _chgsignf, _chgsignl
Odwraca znak argument zmiennoprzecinkowy.  
  
## <a name="syntax"></a>Składnia  
  
```  
double _chgsign(   
   double x   
);  
float _chgsignf(  
   float x   
);  
long double _chgsignl(   
   long double x   
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `x`  
 Wartość zmiennoprzecinkowa zostanie zmieniony.  
  
## <a name="return-value"></a>Wartość zwracana  
 `_chgsign` Zwracają wartość, która jest równa wartości argumentu zmiennoprzecinkowego `x`, ale jego znakiem wycofane. Nie ma żadnych zwracany błąd.  
  
## <a name="requirements"></a>Wymagania  
  
|Procedura|Wymagany nagłówek|  
|-------------|---------------------|  
|`_chgsign`|\<float.h — >|  
|`_chgsignf`, `_chgsignl`|\<Math.h >|  
  
 Aby uzyskać więcej informacji o zgodności, zobacz [zgodności](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Zobacz też  
 [Obsługa liczb zmiennoprzecinkowych](../../c-runtime-library/floating-point-support.md)   
 [fabs —, fabsf —, fabsl](../../c-runtime-library/reference/fabs-fabsf-fabsl.md)   
 [copysign —, copysignf —, copysignl —, _copysign — _copysignf —, _copysignl —](../../c-runtime-library/reference/copysign-copysignf-copysignl-copysign-copysignf-copysignl.md)