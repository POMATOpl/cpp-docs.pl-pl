---
title: "Kompilatora (poziom 1) ostrzeżenie C4441 | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4441
dev_langs: C++
helpviewer_keywords: C4441
ms.assetid: 7fc540a5-e41f-47cf-aa37-b2b699c2685e
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 33337741819d908ce9445d82d905ecfc5738acda
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4441"></a>Kompilator C4441 ostrzegawcze (poziom 1)
Konwencja wywołania "cc1" ignorowane. Zamiast tego użyć "cc2"  
  
 Należy użyć funkcji Członkowskich w zarządzanych typy danych zdefiniowane przez użytkownika i typami ogólnymi funkcji globalnej [__clrcall](../../cpp/clrcall.md) konwencji wywoływania.  Kompilator używane `__clrcall`.  
  
## <a name="example"></a>Przykład  
 Poniższy przykład generuje C4441.  
  
```  
// C4441.cpp  
// compile with: /clr /W1 /c  
generic <class ItemType>  
void __cdecl Test(ItemType item) {}   // C4441  
// try the following line instead  
// void Test(ItemType item) {}  
  
ref struct MyStruct {  
   void __cdecl Test(){}   // C4441  
   void Test2(){}   // OK  
};  
```