---
title: "C2638 błąd kompilatora | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2638
dev_langs: C++
helpviewer_keywords: C2638
ms.assetid: 9d4275e8-406d-455e-afee-3a37799230e0
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: fff25798e1878a69e8e6310c71a687af23134d53
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2638"></a>C2638 błąd kompilatora
"identyfikator": modyfikator __based jest niedozwolony we wskaźniku do elementu członkowskiego  
  
 `__based` Modyfikatora nie można używać dla wskaźników do elementów członkowskich.  
  
 Poniższy przykład generuje C2638:  
  
```  
// C2638.cpp  
void *a;  
  
class C {  
public:  
   int i;  
   int j;  
   int func();  
};  
int __based (a) C::* cpi = &C::i;  // C2638  
int (__based (a) C::* cpf)() = &C::func; // c2638  
```