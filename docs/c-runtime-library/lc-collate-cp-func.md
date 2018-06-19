---
title: ___lc_collate_cp_func | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
apiname:
- ___lc_collate_cp_func
apilocation:
- msvcr120.dll
- msvcrt.dll
- msvcr100.dll
- msvcr80.dll
- msvcr110_clr0400.dll
- msvcr110.dll
- msvcr90.dll
apitype: DLLExport
f1_keywords:
- ___lc_collate_cp_func
dev_langs:
- C++
helpviewer_keywords:
- ___lc_collate_cp_func
ms.assetid: 46ccc084-7ac9-4e5d-9138-e12cb5845615
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cd67abc48af35b5e538b8ad1928269d10f9a71aa
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/03/2018
ms.locfileid: "32389133"
---
# <a name="lccollatecpfunc"></a>___lc_collate_cp_func
Funkcji CRT wewnętrznej. Pobiera bieżącej stronie kodowej sortowania wątku.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
UINT ___lc_codepage_func(void);  
```  
  
## <a name="return-value"></a>Wartość zwracana  
 Bieżąca strona kodowa sortowania wątku.  
  
## <a name="remarks"></a>Uwagi  
 `___lc_collate_cp_func` jest wewnętrzny funkcji CRT, która jest używana przez inne funkcje CRT można uzyskać z magazynu lokalnego wątku CRT danych bieżącej stronie kodowej sortowania. Informacje te są również dostępne za pomocą [_get_current_locale —](../c-runtime-library/reference/get-current-locale.md) funkcji.  
  
 Funkcje CRT wewnętrznej są specyficzne dla implementacji i może ulec zmianie z każdym wersję. Nie zaleca się ich użycie w kodzie.  
  
## <a name="requirements"></a>Wymagania  
  
|Procedura|Wymagany nagłówek|  
|-------------|---------------------|  
|`___lc_collate_cp_func`|crt\src\setlocal.h|  
  
## <a name="see-also"></a>Zobacz też  
 [_get_current_locale](../c-runtime-library/reference/get-current-locale.md)   
 [setLocale, _wsetlocale —](../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [_create_locale, _wcreate_locale](../c-runtime-library/reference/create-locale-wcreate-locale.md)   
 [_free_locale](../c-runtime-library/reference/free-locale.md)