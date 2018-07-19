---
title: '_variant_t:: oddziel | Dokumentacja firmy Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _variant_t::Detach
- _variant_t.Detach
dev_langs:
- C++
helpviewer_keywords:
- VARIANT object [C++], detatch
- Detach method [C++]
- VARIANT object
ms.assetid: c348ac08-62cf-4657-a16f-974a79c12158
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f71257b369e7833f279c0f68ce33e0ec925ebf6b
ms.sourcegitcommit: 76fd30ff3e0352e2206460503b61f45897e60e4f
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/13/2018
ms.locfileid: "39026263"
---
# <a name="varianttdetach"></a>_variant_t::Detach
**Microsoft Specific**  
  
 Odłącza zhermetyzowany `VARIANT` obiektu z tego `_variant_t` obiektu.  
  
## <a name="syntax"></a>Składnia  
  
```  
  
VARIANT Detach( );  
  
```  
  
## <a name="return-value"></a>Wartość zwracana  
 Zhermetyzowany `VARIANT`.  
  
## <a name="remarks"></a>Uwagi  
 Wyodrębnia i zwraca zhermetyzowany `VARIANT`, powoduje to wyczyszczenie `_variant_t` obiektu bez niszczenia samego go. Ta funkcja członkowska usuwa `VARIANT` z hermetyzacji i zestawy `VARTYPE` tego `_variant_t` obiektu VT_EMPTY. To pozwala zwolnić zwracanego `VARIANT` przez wywołanie metody [VariantClear](http://msdn.microsoft.com/28741d81-8404-4f85-95d3-5c209ec13835) funkcji.  
  
 **END specyficzny dla Microsoft**  
  
## <a name="see-also"></a>Zobacz też  
 [_variant_t, klasa](../cpp/variant-t-class.md)