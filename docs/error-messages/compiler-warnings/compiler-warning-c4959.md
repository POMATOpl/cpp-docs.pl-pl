---
title: "C4959 ostrzeżenia kompilatora | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4959
dev_langs: C++
helpviewer_keywords: C4959
ms.assetid: 3a128f3e-4d8a-4565-ba1a-5d32fdeb5982
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3aa55d1f689bf051b62c60dd797540af3cf6bc73
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-c4959"></a>C4959 ostrzeżenia kompilatora
Nie można zdefiniować niezarządzanego struct "type" w/CLR: Safe, ponieważ dostęp do jego elementów członkowskich implikuje kod niemożliwy do zweryfikowania  
  
 Uzyskiwanie dostępu do elementu członkowskiego typu niezarządzanego utworzy obrazie niemożliwy (peverify.exe).  
  
 Aby uzyskać więcej informacji, zobacz [czystej i weryfikowalny kod (C + +/ CLI)](../../dotnet/pure-and-verifiable-code-cpp-cli.md).  
  
 To ostrzeżenie jest wystawione jako błąd i może być wyłączone z [ostrzeżenie](../../preprocessor/warning.md) pragma lub [/wd](../../build/reference/compiler-option-warning-level.md) — opcja kompilatora.  
  
 Poniższy przykład generuje C4959:  
  
```  
// C4959.cpp  
// compile with: /clr:safe  
  
// Uncomment the following line to resolve.  
// #pragma warning( disable : 4959 )  
struct X {  
   int data;  
};  
  
int main() {  
   X x;  
   x.data = 10;   // C4959  
}  
```