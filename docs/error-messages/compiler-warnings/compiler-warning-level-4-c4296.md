---
title: "Kompilatora (poziom 4) ostrzeżenie C4296 | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4296
dev_langs: C++
helpviewer_keywords: C4296
ms.assetid: 9d99aafe-f6bd-4ee0-b8d0-98ce5712274d
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: af07562daebe4cd6cae0499efafcc9fa3f8b30ee
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4296"></a>Kompilator C4296 ostrzegawcze (poziom 4)
"operator": wyrażenie zawsze ma wartość false  
  
 Niepodpisane zmiennej został użyty w operacji porównania, o wartości zero.  
  
 To ostrzeżenie jest domyślnie wyłączone. Zobacz [kompilatora ostrzeżeń czy są wyłączone domyślnie](../../preprocessor/compiler-warnings-that-are-off-by-default.md) Aby uzyskać więcej informacji.  
  
 Poniższy przykład generuje C4296:  
  
```  
// C4296.cpp  
// compile with: /W4  
#pragma warning(default : 4296)  
int main()  
{  
   unsigned int u = 9;  
   if (u < 0)    // C4296  
      u++;  
   if (u >= 0)   // C4296  
      u++;  
}  
```