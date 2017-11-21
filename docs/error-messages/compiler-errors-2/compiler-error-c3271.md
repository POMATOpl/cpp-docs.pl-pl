---
title: "C3271 błąd kompilatora | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3271
dev_langs: C++
helpviewer_keywords: C3271
ms.assetid: 16d8bd1d-2e30-4c6a-a07f-0c4f3342fab5
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 1dd522a3997e8b95409c9a6089bfdfd3d69a7af2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3271"></a>C3271 błąd kompilatora
"członek": Nieprawidłowa wartość 'value' dla atrybutu FieldOffset  
  
 Wartość ujemną został przekazany do **FieldOffset** atrybutu.  
  
 Poniższy przykład generuje C3271:  
  
```  
// C3271.cpp  
// compile with: /clr /c  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
[StructLayout(LayoutKind::Explicit)]  
value class MyStruct1 {  
   public: [FieldOffset(0)] int a;  
   public: [FieldOffset(-1)] long b;   // C3271  
};  
```  
