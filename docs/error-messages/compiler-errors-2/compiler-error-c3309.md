---
title: "C3309 błąd kompilatora | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3309
dev_langs: C++
helpviewer_keywords: C3309
ms.assetid: 75ee16e3-7d4e-4c41-b3cb-64e9849c3aab
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 528ee8dd3925ee989003db8a484041bb2a3a03dd
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3309"></a>C3309 błąd kompilatora
"macro_name": Nazwa modułu nie może być makrem lub słowem kluczowym  
  
 Wartość, które można przekazać do właściwości name atrybutu modułu nie może być symbol preprocesora rozwinąć; musi on być literałem ciągu.  
  
 Poniższy przykład generuje C3309:  
  
```  
// C3309.cpp  
#define NAME MyModule  
[module(name="NAME")];   // C3309  
// Try the following line instead  
// [module(name="MyModule")];  
[coclass]  
class MyClass {  
public:  
   void MyFunc();  
};  
  
int main() {  
}  
```