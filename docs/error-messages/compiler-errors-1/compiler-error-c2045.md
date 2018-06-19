---
title: C2045 błąd kompilatora | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2045
dev_langs:
- C++
helpviewer_keywords:
- C2045
ms.assetid: 2fca668e-9b20-4933-987a-18c0fd0187df
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f81e22214cf9f89a2b2bcabe1bc484647d7f9c0f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
ms.locfileid: "33172839"
---
# <a name="compiler-error-c2045"></a>C2045 błąd kompilatora
'Identyfikator': Etykieta zdefiniowana ponownie  
  
 Etykieta pojawia się przed użycie wielu instrukcji w tej samej funkcji.  
  
 Poniższy przykład generuje C2045:  
  
```  
// C2045.cpp  
int main() {  
   label: {  
   }  
   goto label;  
   label: {}   // C2045  
}  
```