---
title: "C2054 błąd kompilatora | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2054
dev_langs: C++
helpviewer_keywords: C2054
ms.assetid: 37f7c612-0d7d-4728-9e67-ac4160555f48
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 1ab12a8395f3587f0fbdca5ad821cd9ec2241d25
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2054"></a>C2054 błąd kompilatora
Oczekiwano "(" do wykonania 'Identyfikator'  
  
 Identyfikator funkcji jest używany w kontekście, który wymaga nawiasów końcowe.  
  
 Ten błąd może być spowodowany, pomijając znakiem równości (=) podczas inicjowania złożonych.  
  
 Poniższy przykład generuje C2054:  
  
```  
// C2054.c  
int array1[] { 1, 2, 3 };   // C2054, missing =  
```  
  
 Możliwe rozwiązanie:  
  
```  
// C2054b.c  
int main() {  
   int array2[] = { 1, 2, 3 };  
}  
```