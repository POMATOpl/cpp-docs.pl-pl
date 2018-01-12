---
title: "C2582 błąd kompilatora | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2582
dev_langs: C++
helpviewer_keywords: C2582
ms.assetid: ee1b9378-8bcd-4792-b87e-6d7a466d29ed
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c472270f1420475a71c1e184206b6291ec456a47
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2582"></a>C2582 błąd kompilatora
Funkcja "function" jest niedostępna w "type"  
  
 Nastąpiła próba można przypisać do obiektu, który nie ma operatora przypisania.  
  
 Poniższy przykład generuje C2582:  
  
```  
// C2582.cpp  
// compile with: /clr  
using namespace System;  
  
struct N {};  
ref struct O {};  
ref struct R {  
   property O prop;   // C2582  
   property O ^ prop2;   // OK  
};  
  
int main() {  
   String ^ st1 = gcnew String("");  
   ^st1 = gcnew String("");   // C2582  
   st1 = "xxx";   // OK  
}  
```