---
title: Kompilatora (poziom 1) ostrzeżenie C4178 | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4178
dev_langs:
- C++
helpviewer_keywords:
- C4178
ms.assetid: 2c2c8f97-a5c4-47cd-8dd2-beea172613f3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a85ce7df620485e00d8cef6a83522d82bf496068
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
ms.locfileid: "33277543"
---
# <a name="compiler-warning-level-1-c4178"></a>Kompilator C4178 ostrzegawcze (poziom 1)
Stała przypadku "stała" za duża dla typu wyrażenia switch  
  
 Wielkość stała w `switch` wyrażenia nie mieści się w typie, do której jest przypisany.  
  
## <a name="example"></a>Przykład  
  
```  
// C4178.cpp  
// compile with: /W1  
int main()  
{  
    int i;  // maximum size of unsigned long int is 4294967295  
    switch( i )  
    {  
        case 4294967295:   // OK  
            break;  
        case 4294967296:   // C4178  
            break;  
    }  
 }  
```