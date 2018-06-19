---
title: C2274 błąd kompilatora | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2274
dev_langs:
- C++
helpviewer_keywords:
- C2274
ms.assetid: 8e874903-f499-45ef-8291-f821eee4cc1c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: dfd9bda3f3b0ab267ec008443dd865334e1b765e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
ms.locfileid: "33173028"
---
# <a name="compiler-error-c2274"></a>C2274 błąd kompilatora
'type': niedozwolony po prawej stronie '.' — operator  
  
 Typ jest wyświetlany jako prawy argument operacji operatora dostępu do elementu członkowskiego (.).  
  
 Ten błąd może być spowodowany przez próby uzyskania dostępu konwersji typu zdefiniowanego przez użytkownika. Użyj słowa kluczowego `operator` między okresem i `type`.  
  
 Poniższy przykład generuje C2286:  
  
```  
// C2274.cpp  
struct MyClass {  
   operator int() {  
      return 0;  
   }  
};  
  
int main() {  
   MyClass ClassName;  
   int i = ClassName.int();   // C2274  
   int j = ClassName.operator int();   // OK  
}  
```