---
title: "C2443 błąd kompilatora | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2443
dev_langs: C++
helpviewer_keywords: C2443
ms.assetid: 315330d5-24bc-4193-a531-0642095be58f
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6bfa46218cb131f680192b65dde6dd75a5b86b67
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2443"></a>C2443 błąd kompilatora
konflikt rozmiar operandu  
  
 Instrukcja wymaga argumentów operacji, aby mieć ten sam rozmiar.  
  
 Poniższy przykład generuje C2443:  
  
```  
// C2443.cpp  
// processor: x86  
short var;  
int main() {  
   __asm xchg ax,bl   // C2443  
   __asm mov al,red   // C2443  
   __asm mov al,BYTE PTR var   // OK  
}  
```