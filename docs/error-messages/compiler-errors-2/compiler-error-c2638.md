---
title: C2638 błąd kompilatora | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2638
dev_langs:
- C++
helpviewer_keywords:
- C2638
ms.assetid: 9d4275e8-406d-455e-afee-3a37799230e0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b2917b1a947925b8bbd01f366f9540184b839a41
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
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