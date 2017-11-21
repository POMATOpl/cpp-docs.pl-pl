---
title: "Kompilatora (poziom 1) ostrzeżenie C4183 | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4183
dev_langs: C++
helpviewer_keywords: C4183
ms.assetid: dc48312c-4b34-44dd-80ff-eb5f11d5ca47
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 025509de5f2b3dd14d957422042d8094d137924f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4183"></a>Kompilator C4183 ostrzegawcze (poziom 1)
'Identyfikator': Brak typu zwracanego; przyjęto, że funkcją członkowską zwracającą "int"  
  
 Definicji wbudowanej funkcji Członkowskich w klasie lub strukturze nie ma zwracanego typu. Ta funkcja członkowska przyjęto domyślną zwracany typ `int`.  
  
 Poniższy przykład generuje C4183:  
  
```  
// C4183.cpp  
// compile with: /W1 /c  
#pragma warning(disable : 4430)  
class MyClass1;  
class MyClass2 {  
   MyClass1() {};   // C4183  
};  
```