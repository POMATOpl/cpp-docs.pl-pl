---
title: "Porady: używanie funkcji gcnew do tworzenia typów wartości i użyj niejawnej konwersji Boxing | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- gcnew keyword [C++], creating value types
- boxing, implicit
- value types, creating
ms.assetid: ceb48841-d6bd-47be-a167-57f44c961603
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 759e6e25bcbbdba8928ce80ac92caf65ba81e58a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-use-gcnew-to-create-value-types-and-use-implicit-boxing"></a>Porady: używanie funkcji gcnew do tworzenia typów wartości i korzystanie z niejawnej konwersji boxing
Przy użyciu [gcnew](../windows/ref-new-gcnew-cpp-component-extensions.md) na wartość typu utworzy opakowanym typem wartościowym, który można umieścić na stercie zarządzanej, zbierane w pamięci.  
  
## <a name="example"></a>Przykład  
  
```  
// vcmcppv2_explicit_boxing4.cpp  
// compile with: /clr  
public value class V {  
public:  
   int m_i;  
   V(int i) : m_i(i) {}  
};  
  
public ref struct TC {  
   void do_test(V^ v) {  
      if (v != nullptr)  
         ;  
      else  
         ;  
   }  
};  
  
int main() {  
   V^ v = gcnew V(42);  
   TC^ tc = gcnew TC;  
   tc->do_test(v);  
}  
```  
  
## <a name="see-also"></a>Zobacz też  
 [OPAKOWYWANIE](../windows/boxing-cpp-component-extensions.md)