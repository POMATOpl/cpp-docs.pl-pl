---
title: "C3902 błąd kompilatora | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3902
dev_langs: C++
helpviewer_keywords: C3902
ms.assetid: feb3bb29-f836-4d77-ba71-3876f7f4f216
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7579884bbe0d2c6764a2b5755d3d9bab9835ac71
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3902"></a>C3902 błąd kompilatora
"Metoda dostępu": Typ ostatniego parametru musi być 'type'  
  
 Typ ostatniego parametru co najmniej jedną metodę zestawu musi być zgodna z typem właściwości. Aby uzyskać więcej informacji, zobacz [właściwości](../../windows/property-cpp-component-extensions.md).  
  
 Poniższy przykład generuje C3902:  
  
```  
// C3902.cpp  
// compile with: /clr /c  
using namespace System;  
ref class X {  
   property String ^Name {  
      void set(int);   // C3902  
      // try the following line instead  
      // void set(String^){}  
   }  
  
   property double values[int,int] {  
      void set(int, int, float);   // C3902  
      // try the following line instead  
      // void set(int, int, double){}  
   }  
};  
```