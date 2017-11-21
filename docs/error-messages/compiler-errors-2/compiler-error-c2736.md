---
title: "C2736 błąd kompilatora | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2736
dev_langs: C++
helpviewer_keywords: C2736
ms.assetid: 95a6bc28-c0cb-49dc-87e6-e993dbbba881
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 303ca2ead2411bcc0ceb24ee1329094de2adbb8a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2736"></a>C2736 błąd kompilatora
— słowo kluczowe "— słowo kluczowe" nie jest dozwolone przy rzutowaniu  
  
 Słowo kluczowe jest nieprawidłowa w rzutowanie.  
  
 Poniższy przykład generuje C2736:  
  
```  
// C2736.cpp  
int main() {  
   return (virtual) 0;   // C2736  
   // try the following line instead  
   // return 0;  
}  
```