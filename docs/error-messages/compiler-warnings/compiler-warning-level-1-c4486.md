---
title: "Kompilatora (poziom 1) ostrzeżenie C4486 | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4486
dev_langs: C++
helpviewer_keywords: C4486
ms.assetid: 2c0c59e3-d025-4d97-8da2-fa27df1402fc
caps.latest.revision: "4"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: d8819029a9fc5a40281f875ab12595c7a73f0e09
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4486"></a>Kompilator C4486 ostrzegawcze (poziom 1)
"Funkcja": prywatna metoda wirtualna klasy referencyjnej lub klasy wartości powinna być oznaczona jako "sealed"  
  
 Ponieważ prywatna wirtualna funkcja członkowska klasy zarządzanej lub struktury nie może uzyskać dostępu do lub zastąpione, powinien być oznaczony [zapieczętowanego](../../windows/sealed-cpp-component-extensions.md).  
  
## <a name="example"></a>Przykład  
 Poniższy przykład generuje C4486.  
  
```  
// C4486.cpp  
// compile with: /clr /c /W1  
ref class B {  
private:  
   virtual void f() {}   // C4486  
   virtual void f1() sealed {}   // OK  
};  
```  
  
## <a name="example"></a>Przykład  
 Poniższy przykład przedstawia jedną wykorzystanie prywatnej funkcji zapieczętowanym, wirtualne.  
  
```  
// C4486_b.cpp  
// compile with: /clr /c  
ref class B {};  
  
ref class D : B {};  
  
interface class I {  
   B^ mf();  
};  
  
ref class E : I {  
private:  
   virtual B^ g() sealed = I::mf {  
      return gcnew B;  
   }  
  
public:  
   virtual D^ mf() {  
      return gcnew D;  
   }  
};  
```