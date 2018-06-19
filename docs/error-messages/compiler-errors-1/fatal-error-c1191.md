---
title: Błąd krytyczny C1191 | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1191
dev_langs:
- C++
helpviewer_keywords:
- C1191
ms.assetid: 2888c6c4-b4e6-449e-8ee0-7917f31086df
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bf700db0e415fd7886cd8ba845f06a2d8f6c3249
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
ms.locfileid: "33226346"
---
# <a name="fatal-error-c1191"></a>Błąd krytyczny C1191
'dll' mogą być importowane tylko w zakresie globalnym  
  
 Z instrukcjami, aby zaimportować mscorlib.dll do programu, który używa programowania/CLR nie może występować w przestrzeni nazw lub funkcji, ale musi występować w zakresie globalnym.  
  
 Poniższy przykład generuje C1191:  
  
```  
// C1191.cpp  
// compile with: /clr  
namespace sample {  
   #using <mscorlib.dll>   // C1191 not at global scope  
}  
```  
  
 Możliwe rozwiązanie:  
  
```  
// C1191b.cpp  
// compile with: /clr /c  
#using <mscorlib.dll>  
namespace sample {}  
```