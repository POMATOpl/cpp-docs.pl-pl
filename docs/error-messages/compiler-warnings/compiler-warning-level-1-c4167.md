---
title: "Kompilatora (poziom 1) ostrzeżenie C4167 | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4167
dev_langs: C++
helpviewer_keywords: C4167
ms.assetid: 74a420bd-9371-4167-b1ee-74dd8680f97b
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 68786d5d93d587af745a04d10f9daaf7b2fb734e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4167"></a>Kompilator C4167 ostrzegawcze (poziom 1)
Funkcja: dostępne tylko jako funkcja wewnętrzna  
  
 **Funkcji #pragma** próbuje wymusić kompilatorowi używanie konwencjonalnej wywołanie funkcji, używany w postaci wewnętrznej. Pragma została zignorowana.  
  
 Aby uniknąć tego ostrzeżenia, należy usunąć **funkcji #pragma**.  
  
## <a name="example"></a>Przykład  
  
```  
// C4167.cpp  
// compile with: /W1  
#include <malloc.h>  
#pragma function(_alloca )   // C4167: _alloca() is intrinsic only  
int main(){}  
```