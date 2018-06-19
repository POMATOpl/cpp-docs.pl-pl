---
title: C3041 błąd kompilatora | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3041
dev_langs:
- C++
helpviewer_keywords:
- C3041
ms.assetid: 9df1ae44-3ac7-4c6c-899f-f35ffe7ccf0d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 766536426a0b183299d5028d90197fd058fb6126
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
ms.locfileid: "33247633"
---
# <a name="compiler-error-c3041"></a>C3041 błąd kompilatora
"var": zmienna w klauzuli "copyprivate" musi być prywatna w załączonym kontekście  
  
 Zmienna przekazany do [copyprivate](../../parallel/openmp/reference/copyprivate.md) nie może zostać udostępniony w otaczającym kontekście.  
  
 Poniższy przykład generuje C3041:  
  
```  
// C3041.cpp  
// compile with: /openmp /c  
#include "omp.h"  
double d;  
int main() {  
   #pragma omp parallel shared(d)  
   // try the following line instead  
   // #pragma omp parallel private(d)  
   {  
      // or don't make d copyprivate  
      #pragma omp single copyprivate(d)   // C3041  
      {  
      }  
   }  
}  
```