---
title: "C2669 błąd kompilatora | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2669
dev_langs: C++
helpviewer_keywords: C2669
ms.assetid: f9cb8111-bcdc-484b-a863-2c42e15a0496
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 98413ed9ccd216c2fef9687f248d9e759b283f2e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2669"></a>C2669 błąd kompilatora
Funkcja członkowska nie jest dozwolona w anonimowym związku  
  
[Związki anonimowe](../../cpp/unions.md#anonymous_unions) nie może mieć funkcji elementów członkowskich.  
  
## <a name="example"></a>Przykład  
Poniższy przykład generuje C2669:  
  
```cpp  
// C2669.cpp  
struct X {  
   union {  
      int i;  
      void f() {   // C2669, remove function  
         i = 0;   
      }  
   };  
};  
```  
  