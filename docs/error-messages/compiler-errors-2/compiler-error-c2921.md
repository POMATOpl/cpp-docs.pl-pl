---
title: "C2921 błąd kompilatora | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2921
dev_langs: C++
helpviewer_keywords: C2921
ms.assetid: 323642a0-bfc4-4942-9f41-c3adf5c54296
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a67763ba2c2b8f72f539cdb5528e696eaa700f8b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2921"></a>C2921 błąd kompilatora
Ponowna definicja: "class": szablon klasy lub rodzajowa jest ponownie deklarowany jako "type"  
  
 Klasy ogólne lub szablonu ma wiele deklaracji, które nie są równoważne. Aby naprawić ten błąd, użyj różnych nazw dla różnych typów, lub usuń ponowna definicja nazwy typu.  
  
 Poniższy przykład generuje C2921:  
  
```  
// C2921.cpp  
// compile with: /c  
template <class T> struct TC2 {};  
typedef int TC2;   // C2921  
// try the following line instead  
// typedef struct TC2<int> x;   // OK - declare a template instance   
```  
  
 C2921 może również wystąpić, gdy użycie typów ogólnych.  
  
```  
// C2921b.cpp  
// compile with: /clr /c  
generic <class T> ref struct GC2 {};  
typedef int GC2;   // C2921  
// try the following line instead  
// typedef ref struct GC2<int> x;  
```