---
title: "C2326 błąd kompilatora | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2326
dev_langs: C++
helpviewer_keywords: C2326
ms.assetid: 01a5ea40-de83-4e6f-a4e8-469f441258e0
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 7365b0bfcb3bce1bf765a4dfcf0443524c5b6788
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2326"></a>C2326 błąd kompilatora
"deklarator": funkcja nie może uzyskać dostępu do 'name'  
  
 Kod próbuje zmodyfikować zmiennej członkowskiej, co nie jest możliwe.  
  
## <a name="example"></a>Przykład  
 Poniższy przykład generuje C2326:  
  
```  
// C2326.cpp  
void MyFunc() {  
   int i;  
  
   class MyClass  {  
   public:  
      void mf() {  
         i = 4;   // C2326 i is inaccessible  
      }  
   };  
}  
```