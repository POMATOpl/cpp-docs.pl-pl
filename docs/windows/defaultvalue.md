---
title: DefaultValue | Dokumentacja firmy Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.defaultvalue
dev_langs: C++
helpviewer_keywords: defaultvalue attribute
ms.assetid: efa5d050-b2cc-4d9e-9b8e-79954f218d3a
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 16f75743010087eb13ab38186b6326b4bcc38688
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/24/2017
---
# <a name="defaultvalue"></a>defaultvalue
Umożliwia określenie wartości domyślnej parametru opcjonalnego typu.  
  
## <a name="syntax"></a>Składnia  
  
```  
  
[ defaultvalue= value ]  
```  
  
#### <a name="parameters"></a>Parametry  
 *wartość*  
 Wartość domyślna parametru.  
  
## <a name="remarks"></a>Uwagi  
 **Defaultvalue** atrybut C++ ma te same funkcje co [defaultvalue](http://msdn.microsoft.com/library/windows/desktop/aa366793) MIDL atrybutu.  
  
## <a name="example"></a>Przykład  
 Poniższy kod przedstawia metody interfejsu za pomocą **defaultvalue** atrybutu:  
  
```  
// cpp_attr_ref_defaultvalue.cpp  
// compile with: /LD  
#include <windows.h>  
  
[export] typedef long HRESULT;  
[export, ptr, string] typedef unsigned char * MY_STRING_TYPE;  
  
[  uuid("479B29EE-9A2C-11D0-B696-00A0C903487A"),  
   dual, oleautomation,  
   helpstring("IFireTabCtrl Interface"),  
   helpcontext(122), pointer_default(unique) ]  
  
__interface IFireTabCtrl : IDispatch {  
   [bindable, propget] HRESULT get_Size([out, retval, defaultvalue("33")] long *nSize);  
   [bindable, propput] HRESULT put_Size([in] int nSize);  
};  
  
[ module(name="ATLFIRELib", uuid="479B29E1-9A2C-11D0-B696-00A0C903487A",  
      version="1.0", helpstring="ATLFire 1.0 Type Library") ];  
```  
  
## <a name="requirements"></a>Wymagania  
  
### <a name="attribute-context"></a>Atrybut kontekstu  
  
|||  
|-|-|  
|**Dotyczy**|Parametr — interfejs|  
|**Powtarzalne**|Nie|  
|**Wymaganych atrybutów**|Brak|  
|**Nieprawidłowe atrybuty**|Brak|  
  
 Aby uzyskać więcej informacji, zobacz [konteksty atrybutu](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Zobacz też  
 [Atrybuty IDL](../windows/idl-attributes.md)   
 [Atrybuty parametrów](../windows/parameter-attributes.md)   
 [limit](../windows/out-cpp.md)   
 [retval](../windows/retval.md)   
 [w](../windows/in-cpp.md)   
 [pointer_default —](../windows/pointer-default.md)   
 [unikatowe](../windows/unique-cpp.md)   
