---
title: C2890 błąd kompilatora | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2890
dev_langs:
- C++
helpviewer_keywords:
- C2890
ms.assetid: 49147375-182c-42b1-b170-f475cd436d47
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f23bf91594817e27a681f999d9fb0209ccb90a1c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2890"></a>C2890 błąd kompilatora
"class": klasa ref może mieć tylko jedną klasę podstawową niebędącą interfejsem  
  
 Klasa referencji może mieć tylko jedną klasę podstawową.  
  
 Poniższy przykład generuje C2890:  
  
```  
// C2890.cpp  
// compile with: /clr /c  
ref class A {};  
ref class B {};  
ref class C : public A, public B {};   // C2890  
ref class D : public A {};   // OK  
```  
