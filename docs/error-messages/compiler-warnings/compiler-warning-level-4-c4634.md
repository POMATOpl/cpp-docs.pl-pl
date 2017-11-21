---
title: "Kompilatora (poziom 4) ostrzeżenie C4634 | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4634
dev_langs: C++
helpviewer_keywords: C4634
ms.assetid: 3e3496ce-2ac7-43d0-a48a-f514c950e81d
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: e30bac39692844e5f6cd23cc69bfc850d88a3776
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-4-c4634"></a>Kompilator C4634 ostrzegawcze (poziom 4)
Komentarz dokumentu XML: nie można zastosować: Przyczyna  
  
 Tagów dokumentacji XML nie można zastosować do wszystkich C++ konstrukcje.  Na przykład nie możesz dodać komentarz dokumentacji do przestrzeni nazw lub szablonu.  
  
 Aby uzyskać więcej informacji, zobacz [dokumentacji XML](../../ide/xml-documentation-visual-cpp.md).  
  
## <a name="example"></a>Przykład  
 Poniższy przykład generuje C4634.  
  
```  
// C4634.cpp  
// compile with: /W4 /doc /c  
/// This is a namespace.   // C4634  
namespace hello {  
   class MyClass  {};  
};  
```  
  
## <a name="example"></a>Przykład  
 Poniższy przykład generuje C4634.  
  
```  
// C4634_b.cpp  
// compile with: /W4 /doc /c  
/// This is a template.   // C4634  
template <class T>  
class MyClass  {};  
```