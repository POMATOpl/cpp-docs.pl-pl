---
title: _com_error::WCodeToHRESULT | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_error::WCodeToHRESULT
dev_langs:
- C++
helpviewer_keywords:
- WCodeToHRESULT method [C++]
ms.assetid: 0ec43a4b-ca91-42d5-b270-3fde9c8412ea
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3f777b1de83b19727bca5e1b498c5380604f6688
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/01/2018
ms.locfileid: "39404544"
---
# <a name="comerrorwcodetohresult"></a>_com_error::WCodeToHRESULT
**Microsoft Specific**  
  
 Mapuje 16-bitowych *wcode —* HRESULT 32-bitowych.  
  
## <a name="syntax"></a>Składnia  
  
```    
static HRESULT WCodeToHRESULT(  
   WORD wCode   
) throw( );  
```  
  
#### <a name="parameters"></a>Parametry  
 *Wcode —*  
 16-bitowych *wcode —* mają być mapowane na HRESULT 32-bitowych.  
  
## <a name="return-value"></a>Wartość zwracana  
 32-bitowych HRESULT mapowane z 16-bitowych *wcode —*.  
  
## <a name="remarks"></a>Uwagi  
 Zobacz [wcode —](../cpp/com-error-wcode.md) funkcja elementu członkowskiego.  
  
 **END specyficzny dla Microsoft**  
  
## <a name="see-also"></a>Zobacz także  
 [_com_error::WCode](../cpp/com-error-wcode.md)   
 [_com_error::HRESULTToWCode](../cpp/com-error-hresulttowcode.md)   
 [_com_error, klasa](../cpp/com-error-class.md)