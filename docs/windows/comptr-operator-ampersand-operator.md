---
title: ComPtr::operator&amp; Operator | Dokumentacja firmy Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: client/Microsoft::WRL::ComPtr::operator&
dev_langs: C++
helpviewer_keywords: operator& operator
ms.assetid: 2d77fda6-f4b2-45c1-8a0e-fbc355013531
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 2b464a77fedf0d996210040b744faea0ee7372ef
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/24/2017
---
# <a name="comptroperatoramp-operator"></a>ComPtr::operator&amp; — Operator
Zwalnia skojarzony z tym interfejs `ComPtr` obiekt, a następnie pobiera adres `ComPtr` obiektu.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
Details::ComPtrRef<WeakRef> operator&()  
  
const Details::ComPtrRef<const WeakRef> operator&() const  
```  
  
## <a name="return-value"></a>Wartość zwracana  
 Słabe odwołanie do bieżącego `ComPtr`.  
  
## <a name="remarks"></a>Uwagi  
 Ta metoda różni się od [ComPtr::GetAddressOf](../windows/comptr-getaddressof-method.md) , ta metoda zwalnia odwołanie do wskaźnika interfejsu. Użyj `ComPtr::GetAddressOf` Jeżeli adresu wskaźnika interfejsu, ale nie mają być wersji interfejsu.  
  
## <a name="requirements"></a>Wymagania  
 **Nagłówek:** client.h  
  
 **Namespace:** Microsoft::wrl —  
  
## <a name="see-also"></a>Zobacz też  
 [Comptr — klasa](../windows/comptr-class.md)