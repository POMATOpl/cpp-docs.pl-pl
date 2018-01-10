---
title: "Kompilatora (poziom 1) ostrzeżenie C4533 | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4533
dev_langs: C++
helpviewer_keywords: C4533
ms.assetid: 359fecda-d540-46e5-b214-dbabe9ef50d2
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d2cf5a2c4cf663aab73279fc9ff0e0a9c878127b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4533"></a>Kompilator C4533 ostrzegawcze (poziom 1)
Inicjalizacja "Zmienna" jest pomijana przy "instrukcji"  
  
 Instrukcji w programie zmienić przepływu sterowania, w taki sposób, że nie została wykonana instrukcja zainicjować zmiennej. Poniższy przykład generuje C4533:  
  
```  
// C4533.cpp  
// compile with: /W1  
#include <stdio.h>  
  
struct A  
{  
   int m_data;  
};  
  
int main()  
{  
   if (1)  
   {  
      goto Label;  
   }  
  
   A a = { 100 };  
  
   Label:   // C4533  
      printf("\n%d", a.m_data);   // prints an uninitialized value  
}  
```