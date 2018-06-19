---
title: C2054 błąd kompilatora | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2054
dev_langs:
- C++
helpviewer_keywords:
- C2054
ms.assetid: 37f7c612-0d7d-4728-9e67-ac4160555f48
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cfb6d7bf69885d2ac5bf59947ea9f2f70c797003
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
ms.locfileid: "33170378"
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