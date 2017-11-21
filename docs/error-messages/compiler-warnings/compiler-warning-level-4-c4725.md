---
title: "Kompilatora (poziom 4) ostrzeżenie C4725 | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4725
dev_langs: C++
helpviewer_keywords: C4725
ms.assetid: effa0335-71c3-4b3b-8618-da4b9b46a95d
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 1a8b687257c3c00d37104e4a4f900f7e1e4af8e6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-4-c4725"></a>Kompilator C4725 ostrzegawcze (poziom 4)
Instrukcja może być niedokładna na niektórych procesorach Pentium  
  
 Kod zawiera instrukcję zestaw wbudowany, który może dać wyniki niedokładna na niektórych mikroprocesorami Pentium.  
  
 Poniższy przykład generuje C4725:  
  
```  
// C4725.cpp  
// compile with: /W4  
// processor: x86  
double m32fp = 2.0003e-17;  
  
void f() {  
   __asm  
   {  
      FDIV m32fp   // C4725  
   }  
}  
  
int main() {  
}  
```