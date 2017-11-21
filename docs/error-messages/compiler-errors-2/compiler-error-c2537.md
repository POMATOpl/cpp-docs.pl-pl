---
title: "C2537 błąd kompilatora | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2537
dev_langs: C++
helpviewer_keywords: C2537
ms.assetid: aee81d8e-300e-4a8b-b6c4-b3828398b34e
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 610fe53b68ccfa9f0ec187356a737e67837656a4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2537"></a>C2537 błąd kompilatora
"specyfikatora": Niedozwolona specyfikacja powiązania  
  
 Możliwe przyczyny:  
  
1.  Specyfikator połączenie nie jest obsługiwane. Obsługiwane jest tylko specyfikator powiązania "C".  
  
2.  Powiązania "C" określono więcej niż jedną funkcję w zestawie przeciążonej funkcji. Jest to niedozwolone.  
  
 Poniższy przykład generuje C2537:  
  
```  
// C2537.cpp  
// compile with: /c  
extern "c" void func();   // C2537  
extern "C" void func2();   // OK  
```