---
title: "ciąg (C++) | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- vc-attr.string
dev_langs:
- C++
helpviewer_keywords:
- string attribute
ms.assetid: ddde900a-2e99-4fcd-86e8-57e1bdba7c93
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7579dc9d3f7aec17982a0f60e20719c0b52eda42
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/21/2017
---
# <a name="string-c"></a>string (C++)
Oznacza to, że jednowymiarowej tablicy `char`, `wchar_t`, **bajtów** (lub równoważnego) tablicy lub wskaźnika do tablicy takie muszą być traktowane jako ciąg.  
  
## <a name="syntax"></a>Składnia  
  
```  
  
[string]  
  
```  
  
## <a name="remarks"></a>Uwagi  
 **Ciąg** atrybut C++ ma te same funkcje co [ciąg](http://msdn.microsoft.com/library/windows/desktop/aa367270) MIDL atrybutu.  
  
## <a name="example"></a>Przykład  
 Poniższy kod przedstawia sposób użycia **ciąg** w interfejsie i jako element typedef:  
  
```  
// cpp_attr_ref_string.cpp  
// compile with: /LD  
#include "unknwn.h"  
[module(name="ATLFIRELib")];  
[export, string] typedef char a[21];  
[dispinterface, restricted, uuid("00000000-0000-0000-0000-000000000001")]  
__interface IFireTabCtrl  
{  
   [id(1)] HRESULT Method3([in, string] char *pC);  
};  
```  
  
## <a name="requirements"></a>Wymagania  
  
### <a name="attribute-context"></a>Atrybut kontekstu  
  
|||  
|-|-|  
|**Dotyczy**|Tablicy lub wskaźnika do tablicy, interfejs parametrów, metody interfejsu|  
|**Powtarzalne**|Nie|  
|**Wymaganych atrybutów**|Brak|  
|**Nieprawidłowe atrybuty**|Brak|  
  
 Aby uzyskać więcej informacji na temat konteksty atrybutu, zobacz [konteksty atrybutu](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Zobacz też  
 [Atrybuty IDL](../windows/idl-attributes.md)   
 [Atrybuty tablicy](../windows/array-attributes.md)   
 [export](../windows/export.md)   
