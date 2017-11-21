---
title: "btowc — | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: btowc
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
f1_keywords: btowc
dev_langs: C++
helpviewer_keywords: btowc function
ms.assetid: 99a46e02-6f86-4569-af79-5feca012add8
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 71af03a57886b150d6543e3aa11bfb0e05896890
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/24/2017
---
# <a name="btowc"></a>btowc
Określanie, czy liczba całkowita reprezentuje prawidłową znaków jednobajtowych w stanie początkowego przesunięcia.  
  
## <a name="syntax"></a>Składnia  
  
```  
wint_t btowc(  
   int c  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `c`  
 Liczba całkowita do testowania.  
  
## <a name="return-value"></a>Wartość zwracana  
 Zwraca reprezentację znaków dwubajtowych znaku, jeśli całkowitej reprezentuje prawidłową znaków jednobajtowych w stanie początkowego przesunięcia. Zwraca weof — Jeśli ta liczba całkowita jest EOF lub nie jest prawidłowym znakiem jednobajtowe w stanie początkowego przesunięcia. Dane wyjściowe z tej funkcji zależy od bieżącego `LC_TYPE` ustawień regionalnych.  
  
## <a name="requirements"></a>Wymagania  
  
|Procedura|Wymagany nagłówek|  
|-------------|---------------------|  
|`btowc`|\<stdio.h > lub \<wchar.h >|  
  
 Aby uzyskać dodatkowe informacje o zgodności, zobacz [zgodności](../../c-runtime-library/compatibility.md) we wprowadzeniu.  
  
## <a name="see-also"></a>Zobacz też  
 [mbtowc —, _mbtowc_l —](../../c-runtime-library/reference/mbtowc-mbtowc-l.md)