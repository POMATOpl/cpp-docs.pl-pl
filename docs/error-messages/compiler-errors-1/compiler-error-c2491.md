---
title: "C2491 błąd kompilatora | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2491
dev_langs:
- C++
helpviewer_keywords:
- C2491
ms.assetid: 4e5a8f81-124e-402c-a5ec-d35a89b5469e
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fec3aba1430849b68076328db8c1084a2bca3221
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2491"></a>C2491 błąd kompilatora
"identyfikator": definicja dllimport funkcja nie jest dozwolona  
  
 Dane statyczne elementy członkowskie danych i funkcji mogą być deklarowane jako `dllimport`s, ale nie jest zdefiniowany jako `dllimport`s.  
  
 Aby rozwiązać ten problem, Usuń `__declspec(dllimport)` specyfikator w definicji funkcji.  
  
 Poniższy przykład generuje C2491:  
  
```  
// C2491.cpp  
// compile with: /c  
// function definition  
void __declspec(dllimport) funcB() {}   // C2491  
  
// function declaration  
void __declspec(dllimport) funcB();   // OK  
```