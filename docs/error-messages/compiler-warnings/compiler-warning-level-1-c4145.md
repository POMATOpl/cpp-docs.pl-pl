---
title: "Kompilatora (poziom 1) ostrzeżenie C4145 | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4145
dev_langs:
- C++
helpviewer_keywords:
- C4145
ms.assetid: 0440777a-cca2-4159-aff5-e67a254ad64a
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 56f447fb58f8c8b89afd66d9e9cb906ea261e31a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4145"></a>Kompilator C4145 ostrzegawcze (poziom 1)
"wyrażenie1": wyrażenie relacyjne jako wyrażenie przełącznik; możliwa pomyłka z "wyrażenie2"  
  
 A `switch` instrukcja używa wyrażenie relacyjne jako wyrażenie jego kontroli, której wynikiem jest wartość logiczna dla **przypadku** instrukcje. Czy chodziło *wyrażenie2*?  
  
## <a name="example"></a>Przykład  
 Poniższy przykład generuje C4145:  
  
```  
// C4145.cpp  
// compile with: /W1  
int main() {  
   int i = 0;  
   switch(i == 1) {   // C4145, use i instead of i == 1 to resolve  
      case 1:  
         break;  
      default:  
         break;  
   }  
}  
```