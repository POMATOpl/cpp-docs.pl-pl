---
title: C3880 błąd kompilatora | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3880
dev_langs:
- C++
helpviewer_keywords:
- C3880
ms.assetid: b0e05d1e-32d0-4034-9246-f37d23573ea9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 34cc36f3b5fb9571a707e4ffe4e75182e984e407
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3880"></a>C3880 błąd kompilatora
"var": nie może być literałem elementu członkowskiego danych  
  
 Typ [literału](../../windows/literal-cpp-component-extensions.md) atrybut musi być, lub możliwe do przekonwertowania kompilacji do jednego z następujących typów:  
  
-   Typ całkowity  
  
-   string  
  
-   wyliczenia z typu całkowitego lub podstawowej  
  
 Poniższy przykład generuje C3880:  
  
```  
// C3880.cpp  
// compile with: /clr /c  
ref struct Y1 {  
   literal System::Decimal staticConst1 = 10;   // C3880  
   literal int staticConst2 = 10;   // OK  
};  
```