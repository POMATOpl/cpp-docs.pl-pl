---
title: "Kompilatora (poziom 1) ostrzeżenie C4333 | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4333
dev_langs:
- C++
helpviewer_keywords:
- C4333
ms.assetid: d3763c52-6110-4da0-84db-5264e3f3f166
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 22704292cae37b4c4395c49fb69fb2c59c1ccd48
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4333"></a>Kompilator C4333 ostrzegawcze (poziom 1)
"operator": przesunięcie w prawo o zbyt dużą liczbę, utrata danych  
  
 Operacja przesunięcia w prawo była zbyt duża.  Wszystkie znaczących bitów zostaną przesunięte wychodzących i wynik zawsze będzie zerem.  
  
## <a name="example"></a>Przykład  
 Poniższy przykład generuje C4333.  
  
```  
// C4333.cpp  
// compile with: /c /W1  
unsigned shift8 (unsigned char c) {  
   return c >> 8;   // C4333  
  
   // try the following line instead  
   // return c >> 4;   // OK  
}  
```