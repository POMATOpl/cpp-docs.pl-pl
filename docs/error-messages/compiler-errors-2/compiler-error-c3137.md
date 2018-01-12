---
title: "C3137 błąd kompilatora | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3137
dev_langs: C++
helpviewer_keywords: C3137
ms.assetid: 70bb1313-2e87-43ed-a0d8-33fa6ff475e4
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a78907f287b8a4b8a6d5075dab77461259580386
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3137"></a>C3137 błąd kompilatora
"właściwość": nie można zainicjować właściwości  
  
 Właściwości nie można zainicjować, na przykład w liście inicjowania konstruktora.  
  
 Poniższy przykład generuje C3137:  
  
```  
// C3137.cpp  
// compile with: /clr /c  
ref class CMyClass {  
public:  
   property int Size {  
      int get() {  
         return 0;  
      }  
      void set( int i ) {}  
   }  
  
   CMyClass() : Size( 1 ) {   // C3137  
      // to resolve this C3137, remove the initializer from the  
      // ctor declaration and perform the assignment as follows  
      // Size = 1;  
   }  
};  
```  
