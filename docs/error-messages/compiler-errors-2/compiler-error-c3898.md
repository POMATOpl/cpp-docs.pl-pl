---
title: C3898 błąd kompilatora | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3898
dev_langs:
- C++
helpviewer_keywords:
- C3898
ms.assetid: d9a90df6-87e4-4fe7-ab01-c226ee86bf10
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: baeb6e97549bb55212d336e9f832152abaf7db68
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3898"></a>C3898 błąd kompilatora
"var": elementy członkowskie typu danych może być tylko członkami typów zarządzanych  
  
 [Initonly](../../dotnet/initonly-cpp-cli.md) element członkowski danych został zadeklarowany w klasie macierzystego.  `initonly` Element członkowski danych mogą być deklarowane tylko w klasie CLR.  
  
 Poniższy przykład generuje C3898:  
  
```  
// C3898.cpp  
// compile with: /clr  
struct Y1 {  
   initonly  
   static int data_var = 9;   // C3898  
};  
```  
  
 Możliwe rozwiązanie:  
  
```  
// C3898b.cpp  
// compile with: /clr /c  
ref struct Y1 {  
   initonly  
   static int data_var = 9;  
};  
```