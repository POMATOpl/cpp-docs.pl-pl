---
title: "C2971 błąd kompilatora | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2971
dev_langs: C++
helpviewer_keywords: C2971
ms.assetid: fdb5467b-9a41-41ef-ac20-2e9428d5a4fc
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9cf5dfdc80db11803f0060daf5aeb47701a08816
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2971"></a>C2971 błąd kompilatora
"class": parametr szablonu "param": "arg": zmienna lokalna nie może służyć jako argument bez typu  
  
 Jako argument szablonu nie można użyć nazwy lub adresu zmiennej lokalnej.  
  
 Poniższy przykład generuje C2971:  
  
```  
// C2971.cpp  
template <int *pi>   
class Y {};  
  
int global_var = 0;  
  
int main() {  
   int local_var = 0;  
   Y<&local_var> aY;   // C2971  
   // try the following line instead  
   // Y<&global_var> aY;  
}  
```