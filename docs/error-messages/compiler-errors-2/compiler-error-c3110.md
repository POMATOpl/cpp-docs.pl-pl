---
title: "C3110 błąd kompilatora | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3110
dev_langs: C++
helpviewer_keywords: C3110
ms.assetid: 821dc71f-896e-4b2d-af0e-aa9932934b7b
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ec824ca430ea336d6bec1bb43af31201531803a5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3110"></a>C3110 błąd kompilatora
"nazwa_funkcji": nie można przeciążyć metody interfejsu COM  
  
 Interfejs, który jest poprzedzone przez atrybut interfejsu, takich jak:  
  
-   [niestandardowe](../../windows/custom-cpp.md)  
  
-   [dispinterface](../../windows/dispinterface.md)  
  
-   [dual](../../windows/dual.md)  
  
-   [object](../../windows/object-cpp.md)  
  
 nie może być przeciążony. Na przykład:  
  
```  
// C3110.cpp  
#include <unknwn.h>  
[ object, uuid= "4F98A180-EF37-11D1-978D-0000F805D73B" ]  
__interface ITestInterface  
{  
   HRESULT mf1(void);  
   HRESULT mf1(BSTR); // C3110  
};  
  
int main()  
{  
}  
```