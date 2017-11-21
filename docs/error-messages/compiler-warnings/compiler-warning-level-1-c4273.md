---
title: "Kompilatora (poziom 1) ostrzeżenie C4273 | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4273
dev_langs: C++
helpviewer_keywords: C4273
ms.assetid: cc18611d-9454-40a4-ad73-69823d5888fb
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 656ab0c0ee4e5ab0c075329a3d20410c4acc8ac4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4273"></a>Kompilator C4273 ostrzegawcze (poziom 1)
"Funkcja": niespójne powiązanie biblioteki DLL  
  
 Dwie definicje w pliku różnią się w ich stosowania [dllimport](../../cpp/dllexport-dllimport.md).  
  
## <a name="example"></a>Przykład  
 Poniższy przykład generuje C4273.  
  
```  
// C4273.cpp  
// compile with: /W1 /c  
char __declspec(dllimport) c;  
char c;   // C4273, delete this line or the line above to resolve  
```  
  
## <a name="example"></a>Przykład  
 Poniższy przykład generuje C4273.  
  
```  
// C4273_b.cpp  
// compile with: /W1 /clr /c  
#include <stdio.h>  
extern "C" int printf_s(const char *, ...);   // C4273  
```