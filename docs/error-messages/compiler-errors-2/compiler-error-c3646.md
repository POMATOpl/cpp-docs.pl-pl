---
title: C3646 błąd kompilatora | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3646
dev_langs:
- C++
helpviewer_keywords:
- C3646
ms.assetid: 4391ead2-9637-4ca3-aeda-5a991b18d66d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3ad0a7f16b54d2a06586bdb4c26c87dbcf9ae7b4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3646"></a>C3646 błąd kompilatora
"specyfikatora": nieznany specyfikator przesłonięcia  
  
 Kompilator znaleziono token na pozycji, których ona Oczekiwano znalezienia specyfikator przesłonięcia, ale token nie został rozpoznany przez kompilator.  
  
 Aby uzyskać więcej informacji, zobacz [specyfikatory Override](../../windows/override-specifiers-cpp-component-extensions.md).  
  
 Poniższy przykład generuje C3646:  
  
```  
// C3646.cpp  
// compile with: /clr /c  
ref class C {  
   void f() unknown;   // C3646  
   // try the following line instead  
   // virtual void f() abstract;  
};  
```