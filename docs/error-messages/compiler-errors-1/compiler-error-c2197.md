---
title: "C2197 błąd kompilatora | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2197
dev_langs: C++
helpviewer_keywords: C2197
ms.assetid: 6dd5a6ec-bc80-41b9-a4ac-46f80eaca42d
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e8c33f8db9d5996f4cce84051b6a26b77f8ea94b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2197"></a>C2197 błąd kompilatora
"Funkcja": za dużo argumentów dla wywołania  
  
 Kompilator wykryto zbyt wiele parametrów wywołania funkcji lub deklaracji Niepoprawna funkcja.  
  
 Poniższy przykład generuje C2197:  
  
```  
// C2197.c  
// compile with: /Za /c  
void func( int );  
int main() {  
   func( 1, 2 );   // C2197 two actual parameters  
   func( 2 );   // OK  
}  
```