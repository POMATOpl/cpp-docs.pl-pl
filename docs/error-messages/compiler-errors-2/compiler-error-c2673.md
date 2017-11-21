---
title: "C2673 błąd kompilatora | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2673
dev_langs: C++
helpviewer_keywords: C2673
ms.assetid: 780230c0-619b-4a78-b01d-ff5886306741
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 551801e5d13f18335d30fb1ea37ad29ca27aa777
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2673"></a>C2673 błąd kompilatora
"Funkcja": funkcje globalne nie posiadają wskaźników "this"  
  
 Funkcja globalna próbował uzyskać dostęp do `this`.  
  
 Poniższy przykład generuje C2673:  
  
```  
// C2673.cpp  
int main() {  
   this = 0;   // C2673  
}  
```