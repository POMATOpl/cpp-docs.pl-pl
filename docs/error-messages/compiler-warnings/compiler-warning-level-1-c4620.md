---
title: "Kompilatora (poziom 1) ostrzeżenie C4620 | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4620
dev_langs: C++
helpviewer_keywords: C4620
ms.assetid: fed29934-b797-47e8-bbea-c7e5f8dd6e93
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f550a857f1799e32d599231348123e3f85a0dfd5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4620"></a>Kompilator C4620 ostrzegawcze (poziom 1)
nie przyrostkowej formy "operator ++" znaleziono dla typu "type", użyta zostanie forma przedrostkowa  
  
 Nie istnieje żaden operator inkrementacji przyrostek zdefiniowane dla danego typu. Kompilator używany operator przeciążone prefiks.  
  
 To ostrzeżenie można uniknąć, definiując przyrostek `++` operatora. Utwórz wersję dwuargumentowej `++` operatora, jak pokazano poniżej:  
  
```  
// C4620.cpp  
// compile with: /W1  
class A  
{  
public:  
   A(int nData) : m_nData(nData)  
   {  
   }  
  
   A operator++()  
   {  
      m_nData -= 1;  
      return *this;  
   }  
  
   // A operator++(int)  
   // {  
   //    A tmp = *this;  
   //    m_nData -= 1;  
   //    return tmp;  
   // }  
  
private:  
   int m_nData;  
};  
  
int main()  
{  
   A a(10);  
   ++a;  
   a++;   // C4620  
}  
```