---
title: "C2309 błąd kompilatora | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2309
dev_langs: C++
helpviewer_keywords: C2309
ms.assetid: 6303d5b5-72cf-42b8-92ce-b1eb48e80d48
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 38ecc65572ccc0662eac1e5653474d38447697da
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2309"></a>C2309 błąd kompilatora
przy obsłudze catch Oczekiwano deklaracji wyjątku ujętego w nawiasy  
  
 Obsługa catch nie ma ujętego w nawiasy typu.  
  
 Poniższy przykład generuje C2309:  
  
```  
// C2309.cpp  
// compile with: /EHsc  
#include <eh.h>  
class C {};  
int main() {  
   try {  
      throw "ooops!";  
   }  
   catch C {}   // C2309  
   // try the following line instead  
   // catch( C ) {}  
}  
```