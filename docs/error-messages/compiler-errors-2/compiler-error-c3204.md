---
title: "C3204 błąd kompilatora | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3204
dev_langs: C++
helpviewer_keywords: C3204
ms.assetid: 06e578da-0262-48c8-b2ae-be1cd6d28884
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 7d28da9839a82c63017d8cbd24e585e3af8aab2f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3204"></a>C3204 błąd kompilatora
"_alloca" nie można wywołać z wnętrza bloku catch  
  
 Ten błąd występuje, gdy używasz wywołanie [_alloca](../../c-runtime-library/reference/alloca.md) z wnętrza bloku catch.  
  
## <a name="example"></a>Przykład  
 Poniższy przykład generuje C3204:  
  
```  
// C3204.cpp  
// compile with: /EHsc  
#include <malloc.h>  
  
void ShowError(void)  
{  
   try  
   {  
   }  
   catch(...)  
   {  
      _alloca(1);   // C3204  
   }  
}  
```