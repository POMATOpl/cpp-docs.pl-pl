---
title: "C2781 błąd kompilatora | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2781
dev_langs: C++
helpviewer_keywords: C2781
ms.assetid: f29b9963-f55b-427c-8db6-50f37713df5a
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 71358a4f8082591a5d54c93e7874fc5d26ba18ad
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2781"></a>C2781 błąd kompilatora
"deklaracją": oczekuje co najmniej wartość1 argumentu - wartość2 podana  
  
 Funkcja szablonu z zmiennej listy parametrów ma za mało argumentów.  
  
 Poniższy przykład generuje C2781:  
  
```  
// C2781.cpp  
template<typename T>  
void f(T, T, ...){}  
  
int main() {  
   f(1);   // C2781  
  
   // try the following line instead  
   f(1,1);  
}  
```