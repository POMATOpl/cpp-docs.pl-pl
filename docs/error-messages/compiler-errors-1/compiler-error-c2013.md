---
title: "C2013 błąd kompilatora | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2013
dev_langs: C++
helpviewer_keywords: C2013
ms.assetid: 6b5c955c-53da-48ee-8533-64ef5b905173
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0cb859c54cc0fd4762041b885c7b8e9b6c4a04e8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2013"></a>C2013 błąd kompilatora
Brak ">"  
  
 `#include` Dyrektywy nie ma tagu zamykającego nawiasu ostrego. Dodaj zamykający nawias kwadratowy, aby rozwiązać problem.  
  
 Poniższy przykład generuje C2013:  
  
```  
// C2013.cpp  
#include <stdio.h    // C2013  
```  
  
 Możliwe rozwiązanie:  
  
```  
// C2013b.cpp  
// compile with: /c  
#include <stdio.h>  
```