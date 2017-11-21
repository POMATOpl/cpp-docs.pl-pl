---
title: "Kompilatora (poziom 4) ostrzeżenie C4201 | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4201
dev_langs: C++
helpviewer_keywords: C4201
ms.assetid: 6156f508-9393-4d77-9e73-1ec3e1c32d0d
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: a458c630c0137aa0fb293c0927e079437a538b61
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-4-c4201"></a>Kompilator C4201 ostrzegawcze (poziom 4)
użyto niestandardowego rozszerzenia: typ struct/union  
  
 W obszarze rozszerzenia Microsoft (/Ze) można określić struktury bez deklaratorze jako elementy członkowskie innego struktury lub związku. Te struktury generuje błąd w obszarze Zgodność ANSI ([/Za](../../build/reference/za-ze-disable-language-extensions.md)).  
  
## <a name="example"></a>Przykład  
  
```  
// C4201.cpp  
// compile with: /W4  
struct S  
{  
   float y;  
   struct  
   {  
      int a, b, c;  // C4201  
   };  
} *p_s;  
  
int main()  
{  
}  
```