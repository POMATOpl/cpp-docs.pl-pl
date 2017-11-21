---
title: "C3351 błąd kompilatora | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3351
dev_langs: C++
helpviewer_keywords: C3351
ms.assetid: c021bbbe-1067-4f51-af4f-940d2b792eb5
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: c6a449d904e0b5122ec1a8d2ae9734a6dd3f8b00
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3351"></a>C3351 błąd kompilatora
"object": Konstruktor delegata: drugi argument musi być adresem funkcji globalnej lub statycznej funkcji członkowskiej  
  
 Kompilator oczekiwano adresu funkcja zadeklarowana `static`.  
  
 Poniższy przykład generuje C3351:  
  
```  
// C3351a.cpp  
// compile with: /clr  
delegate int D(int, int);  
  
ref class C {  
public:  
   int mf(int, int) {  
      return 1;  
   }  
  
   static int mf2(int, int) {  
      return 1;  
   }  
};  
  
int main() {  
   System::Delegate ^pD = gcnew D(nullptr, &C::mf);   // C3351  
   System::Delegate ^pD2 = gcnew D(&C::mf2);  
}  
```  
