---
title: "Porady: utrzymywanie odwołania do typu wartości w typie natywnym | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: get-started-article
dev_langs:
- C++
helpviewer_keywords:
- value type reference in native type
- reference to value type in native type
ms.assetid: 1eabf8be-7d4f-4339-9027-48d5c4244483
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 4d567504dbf5fa9bc7a8432fcc34a52c22ccbf90
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-hold-reference-to-value-type-in-native-type"></a>Porady: utrzymywanie odwołania do typu wartości w typie natywnym
Użyj `gcroot` na typ opakowany do przechowywania odwołanie do typu wartości w typie natywnym.  
  
## <a name="example"></a>Przykład  
  
```  
// reference_to_value_in_native.cpp  
// compile with: /clr  
#using <mscorlib.dll>  
#include <vcclr.h>   
  
using namespace System;   
  
public value struct V {  
   String ^str;  
};  
  
class Native {  
public:  
   gcroot< V^ > v_handle;  
};  
  
int main() {  
   Native native;  
   V v;  
   native.v_handle = v;  
   native.v_handle->str = "Hello";  
   Console::WriteLine("String in V: {0}", native.v_handle->str);  
}  
```  
  
```Output  
String in V: Hello  
```  
  
## <a name="see-also"></a>Zobacz też  
 [Korzystanie z międzyoperacyjności języka C++ (niejawna funkcja PInvoke)](../dotnet/using-cpp-interop-implicit-pinvoke.md)