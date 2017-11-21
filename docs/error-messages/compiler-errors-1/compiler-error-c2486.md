---
title: "C2486 błąd kompilatora | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2486
dev_langs: C++
helpviewer_keywords: C2486
ms.assetid: 436da349-6461-4e32-bfca-4f3e620108e2
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: b7f54417beefb9bd2c82763464d0e76ed81bf7ed
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2486"></a>C2486 błąd kompilatora
"__LOCAL_SIZE" dozwolone tylko w funkcji z atrybutem "naked"  
  
 W przypadku wbudowanego zestawu funkcji nazwę `__LOCAL_SIZE` jest zarezerwowana dla funkcji zadeklarowana z [naked](../../cpp/naked-cpp.md) atrybutu.  
  
 Poniższy przykład generuje C2486:  
  
```  
// C2486.cpp  
// processor: x86  
void __declspec(naked) f1() {  
   __asm {  
      mov   eax,   __LOCAL_SIZE  
   }  
}  
void f2() {  
   __asm {  
      mov   eax,   __LOCAL_SIZE   // C2486  
   }  
}  
```