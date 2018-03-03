---
title: "C2785 błąd kompilatora | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2785
dev_langs:
- C++
helpviewer_keywords:
- C2785
ms.assetid: d8d13360-0d00-4815-8475-b49c7f0dc0f3
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9587151175c593e4b1d9d30f45a19ce807c24990
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2785"></a>C2785 błąd kompilatora
"declaration1" i "declaration2" mają różne typy zwracane  
  
 Zwracany typ specjalizacja szablonu funkcji różni się od zwracanego typu szablonu podstawowej funkcji.  
  
### <a name="to-correct-this-error"></a>Aby poprawić ten błąd  
  
1.  Sprawdź wszystkie specjalizacji szablonu funkcji spójności.  
  
## <a name="example"></a>Przykład  
 Poniższy przykład generuje C2785:  
  
```  
// C2785.cpp  
// compile with: /c  
template<class T> void f(T);  
  
template<> int f(int); // C2785  
template<> void f(int); // OK  
```