---
title: "Kompilatora (poziom 1) ostrzeżenie C4020 | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4020
dev_langs: C++
helpviewer_keywords: C4020
ms.assetid: 8c4cd6be-9371-4c8c-b0ff-a5ad367bbab0
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: f4980961746f2711fcf0655dd37b5f37d8d8124e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4020"></a>Kompilator C4020 ostrzegawcze (poziom 1)
"Funkcja": zbyt wiele parametrów rzeczywistych  
  
 Liczba rzeczywistych parametrów w wywołaniu funkcji przekracza liczbę parametrów formalnych w prototypu funkcji lub definicji. Kompilator przekazuje bardzo rzeczywistych parametrów zgodnie z konwencji wywołania funkcji.  
  
 Poniższy przykład generuje C4020:  
  
```  
// C4020.c  
// compile with: /W1 /c  
void f(int);  
int main() {  
   f(1,2);   // C4020  
}  
```  
  
 Możliwe rozwiązanie:  
  
```  
// C4020b.c  
// compile with: /c  
void f(int);  
int main() {  
   f(1);  
}  
```