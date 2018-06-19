---
title: Kompilatora (poziom 1) ostrzeżenie C4353 | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4353
dev_langs:
- C++
helpviewer_keywords:
- C4353
ms.assetid: 6e79f186-ed82-4c95-9923-0ad5bb9c4db1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e7b9974635fabc07f17b9e46b16d163c72b6d3ea
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
ms.locfileid: "33278037"
---
# <a name="compiler-warning-level-1-c4353"></a>Kompilator C4353 ostrzegawcze (poziom 1)
użyto niestandardowego rozszerzenia: stała 0 jako wyrażenie funkcyjne. Zamiast tego użyj funkcji "__noop" — wewnętrzne  
  
 Nie można użyć stałą wartość zero (0) jako wyrażenie funkcyjne. Aby uzyskać więcej informacji, zobacz [__noop](../../intrinsics/noop.md).  
  
 Poniższy przykład generuje C4353:  
  
```  
// C4353.cpp  
// compile with: /W1  
void MyPrintf(void){};  
#define X 0  
#if X  
   #define DBPRINT MyPrint  
#else  
   #define DBPRINT 0   // C4353 expected  
#endif  
int main(){  
DBPRINT();  
}  
```