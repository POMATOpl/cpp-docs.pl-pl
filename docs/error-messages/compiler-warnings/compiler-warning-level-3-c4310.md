---
title: Kompilatora (poziom 3) ostrzeżenie C4310 | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4310
dev_langs:
- C++
helpviewer_keywords:
- C4310
ms.assetid: cba3eca1-f1ed-499c-9243-337446bdbdd8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fd3ab8ba6eb9175ad3f567408faa1f78c09a6f6a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-3-c4310"></a>Kompilator C4310 ostrzegawcze (poziom 3)
Rzutowanie obcina stałą wartość  
  
 Stała wartość jest rzutowania na mniejszy typ. Kompilator wykonuje rzutowania, w którym obcina danych. Poniższy przykład generuje C4310:  
  
```  
// C4310.cpp  
// compile with: /W4  
int main() {  
   long int a;  
   a = (char) 128;   // C4310, use value 0-127 to resolve  
}  
```