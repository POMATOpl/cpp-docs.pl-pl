---
title: _fpclass, _fpclassf | Dokumentacja firmy Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _fpclass
- _fpclassf
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
- fpclass
- _fpclass
- _fpclassf
- math/_fpclass
- float/_fpclass
- math/_fpclassf
dev_langs: C++
helpviewer_keywords:
- fpclass function
- floating-point numbers, IEEE representation
- _fpclass function
- _fpclassf function
ms.assetid: 2774872d-3543-446f-bc72-db85f8b95a6b
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 2e25d66ba7fd25c52758bfb44cc74326c67ce4db
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/24/2017
---
# <a name="fpclass-fpclassf"></a>_fpclass, _fpclassf
Zwraca wartość wskazującą zmiennoprzecinkowe klasyfikacji argumentu.  
  
## <a name="syntax"></a>Składnia  
  
```  
int _fpclass(   
   double x   
);  
  
int _fpclassf(   
   float x   
); /* x64 only */  
```  
  
#### <a name="parameters"></a>Parametry  
 `x`  
 Wartość zmiennoprzecinkowa do testowania.  
  
## <a name="return-value"></a>Wartość zwracana  
 `_fpclass` i `_fpclassf` zwracają wartość całkowitą, wskazującą zmiennoprzecinkowe klasyfikacji argument `x`. Klasyfikacja może mieć jedną z następujących wartości zdefiniowane w \<float.h — >.  
  
|Wartość|Opis|  
|-----------|-----------------|  
|`_FPCLASS_SNAN`|Sygnalizowanie NaN|  
|`_FPCLASS_QNAN`|Quiet NaN|  
|`_FPCLASS_NINF`|Nieskończoności ujemnej (-INF)|  
|`_FPCLASS_NN`|Niezerowy normalized ujemna|  
|`_FPCLASS_ND`|Ujemna nieznormalizowane|  
|`_FPCLASS_NZ`|Ujemna wartość zero (- 0)|  
|`_FPCLASS_PZ`|Dodatnia 0 (+ 0)|  
|`_FPCLASS_PD`|Dodatnie nieznormalizowane|  
|`_FPCLASS_PN`|Dodatnie znormalizowany inną niż zero|  
|`_FPCLASS_PINF`|Nieskończoności dodatniej (+ INF)|  
  
## <a name="remarks"></a>Uwagi  
 `_fpclass` i `_fpclassf` funkcje są określone firmy Microsoft. Są one podobne do [fpclassify —](../../c-runtime-library/reference/fpclassify.md), ale zwrócił więcej szczegółowych informacji dotyczących argument. `_fpclassf` Funkcja jest dostępna, gdy kompilowany dla x64 tylko platformy.  
  
## <a name="requirements"></a>Wymagania  
  
|Funkcja|Wymagany nagłówek|  
|--------------|---------------------|  
|`_fpclass`|\<float.h — >|  
  
 Aby uzyskać więcej informacji zgodności i zgodności, zobacz [zgodności](../../c-runtime-library/compatibility.md).  
  
## <a name="see-also"></a>Zobacz też  
 [Obsługa liczb zmiennoprzecinkowych](../../c-runtime-library/floating-point-support.md)   
 [isNaN _isnan —, _isnanf](../../c-runtime-library/reference/isnan-isnan-isnanf.md)   
 [fpclassify —](../../c-runtime-library/reference/fpclassify.md)