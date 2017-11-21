---
title: "C3284 błąd kompilatora | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3824
dev_langs: C++
helpviewer_keywords: C3284
ms.assetid: e582f316-e9db-4d27-9c70-fdfa737a9d5f
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 60f8335637064acb7e1c2f5c41d4ddca07b51711
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3284"></a>C3284 błąd kompilatora
ograniczenia dla parametru ogólnego "parametru" funkcji "function" musi być zgodna ograniczenia dla parametru ogólnego "parametru" funkcji "function"  
  
 Jako funkcji wirtualnej z taką samą nazwę i zestawu argumentów w klasie podstawowej funkcji wirtualnej ogólnego należy użyć takich samych ograniczeń.  
  
 Poniższy przykład generuje C3284:  
  
```  
// C3284.cpp  
// compile with: /clr /c  
// C3284 expected  
public interface class IGettable {  
   int Get();  
};  
  
public interface class B {  
   generic<typename T>  
   where T : IGettable  
   virtual int mf(T t);  
};  
  
public ref class D : public B {  
public:  
   generic<typename T>  
   // Uncomment the following line to resolve.  
   // where T : IGettable  
   virtual int mf(T t) {  
      return 4;  
   }  
};  
```