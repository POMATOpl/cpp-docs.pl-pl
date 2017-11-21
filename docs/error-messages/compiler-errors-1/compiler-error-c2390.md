---
title: "C2390 błąd kompilatora | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2390
dev_langs: C++
helpviewer_keywords: C2390
ms.assetid: 06b749ee-d072-4db1-b229-715f2c0728b5
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 37803b8eb5034fb3281dcea385b4a0fca462aaf0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2390"></a>C2390 błąd kompilatora
'Identyfikator': niepoprawna Klasa magazynu "specyfikatora"  
  
 Klasa magazynu jest nieprawidłowa dla identyfikatora zakresu globalnego. Domyślna klasa magazynu jest używany zamiast nieprawidłowa klasa.  
  
 Możliwe rozwiązania:  
  
-   Jeśli identyfikator jest funkcją, Zadeklaruj ją z `extern` magazynu.  
  
-   Jeśli identyfikator jest formalny parametr lub zmienna lokalna, Zadeklaruj ją z magazynem automatycznie.  
  
-   Jeśli identyfikator jest zmienną globalną, Zadeklaruj ją z Brak klasy magazynu (automatycznie magazynu).  
  
## <a name="example"></a>Przykład  
  
-   Poniższy przykład generuje C2390:  
  
```  
// C2390.cpp  
register int i;   // C2390  
  
int main() {  
   register int j;   // OK  
}  
```