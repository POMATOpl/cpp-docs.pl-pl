---
title: "C3824 błąd kompilatora | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3824
dev_langs: C++
helpviewer_keywords: C3824
ms.assetid: b6c6adf1-0a29-401c-a06e-616fd50d4c37
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e18e20cb1ffbe6d06060b3001c48f01b8b8b8cbf
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3824"></a>C3824 błąd kompilatora
"członek": ten typ nie może występować w tym kontekście (parametr funkcji, zwracany typ lub statyczny element członkowski)  
  
 Unieruchamiania wskaźników nie może być działać parametrów i zwracanych typów lub zadeklarowany `static`.  
  
## <a name="example"></a>Przykład  
 Poniższy przykład generuje C3824:  
  
```  
// C3824a.cpp  
// compile with: /clr /c  
void func() {  
   static pin_ptr<int> a; // C3824  
   pin_ptr<int> b; // OK  
}  
```  
