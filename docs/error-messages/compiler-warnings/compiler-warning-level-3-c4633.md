---
title: "Kompilatora (poziom 3) ostrzeżenie C4633 | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4633
dev_langs: C++
helpviewer_keywords: C4633
ms.assetid: 6d76f268-ba8c-448b-8e83-b903a18b583b
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a93b660ea7cd4291b3546166d9f7a9c387ea749a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-3-c4633"></a>Kompilator C4633 ostrzegawcze (poziom 3)
Docelowy komentarza dokumentu XML: błąd: Przyczyna  
  
 Nazwa przekazywana do [ \<param >](../../ide/param-visual-cpp.md) przez kompilator nie znaleziono tagu.  
  
 Poniższy przykład generuje C4633:  
  
```  
// C4633.cpp  
// compile with: /clr /doc /LD /W3  
  
/// Text for class MyClass.  
public ref class MyClass {  
   // C4633 remove line for Int3  
   /// <param name="Int1">Used to indicate status.</param>  
   /// <param name="Int3">Used to indicate status.</param>  
   void MyMethod(int Int1) {  
      Int1 = 0;  
      Int1++;  
   }  
};  
```