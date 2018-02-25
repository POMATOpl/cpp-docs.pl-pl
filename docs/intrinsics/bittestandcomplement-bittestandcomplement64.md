---
title: _bittestandcomplement, _bittestandcomplement64 | Dokumentacja firmy Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- _bittestandcomplement64
- _bittestandcomplement64_cpp
- _bittestandcomplement_cpp
- _bittestandcomplement
dev_langs:
- C++
helpviewer_keywords:
- btc instruction
- _bittestandcomplement intrinsic
- _bittestandcomplement64 intrinsic
ms.assetid: 53fa12dd-835e-4e5d-baec-a431c8678806
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7f113afbee0a8ea687b2ff5b73485164e82d8eeb
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/23/2018
---
# <a name="bittestandcomplement-bittestandcomplement64"></a>_bittestandcomplement, _bittestandcomplement64
**Microsoft Specific**  
  
 Generowanie instrukcji, która sprawdza, czy bit `b` adresu `a`, zwraca bieżącą wartość i ustawia bit do jego dopełnieniem.  
  
## <a name="syntax"></a>Składnia  
  
```  
unsigned char _bittestandcomplement(  
   long *a,  
   long b  
);  
unsigned char _bittestandcomplement64(  
   __int64 *a,  
   __int64 b  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 [w, out] `a`  
 Wskaźnik do pamięci do sprawdzenia.  
  
 [in] `b`  
 Pozycja bit do testowania.  
  
## <a name="return-value"></a>Wartość zwracana  
 Bit na określonej pozycji.  
  
## <a name="requirements"></a>Wymagania  
  
|— Wewnętrzne|Architektura|  
|---------------|------------------|  
|`_bittestandcomplement`|x86, ARM, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
|`_bittestandcomplement64`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Plik nagłówka** \<intrin.h >  
  
## <a name="remarks"></a>Uwagi  
 Ta procedura jest dostępna tylko wewnętrznie.  
  
## <a name="example"></a>Przykład  
  
```  
// bittestandcomplement.cpp  
// processor: x86, IPF, x64  
#include <stdio.h>  
#include <intrin.h>  
  
#pragma intrinsic(_bittestandcomplement)  
#ifdef _M_AMD64  
#pragma intrinsic(_bittestandcomplement64)  
#endif  
  
int main()  
{  
   long i = 1;  
   __int64 i64 = 0x1I64;  
   unsigned char result;  
   printf("Initial value: %d\n", i);  
   printf("Testing bit 1\n");  
   result = _bittestandcomplement(&i, 1);  
   printf("Value changed to %d, Result: %d\n", i, result);  
#ifdef _M_AMD64  
   printf("Testing bit 0\n");  
   result = _bittestandcomplement64(&i64, 0);  
   printf("Value changed to %I64d, Result: %d\n", i64, result);  
#endif  
}  
```  
  
## <a name="sample-output"></a>Przykładowe dane wyjściowe  
  
```  
Initial value: 1  
Testing bit 1  
Value changed to 3, Result: 0  
Testing bit 0  
Value changed to 0, Result: 1  
```  
  
**KOŃCOWY określonych firmy Microsoft**  
  
## <a name="see-also"></a>Zobacz też  
 [Funkcje wewnętrzne kompilatora](../intrinsics/compiler-intrinsics.md)