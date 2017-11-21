---
title: "Kompilatora (poziom 1) ostrzeżenie C4180 | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4180
dev_langs: C++
helpviewer_keywords: C4180
ms.assetid: 40c91bd4-37f1-4d59-a4f3-d5ddab68239b
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 4dc48f912e475c58d4602977d08fbc656e7eed30
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4180"></a>Kompilator C4180 ostrzegawcze (poziom 1)
Kwalifikator stosowany do typu funkcji nie ma znaczenia; ignorowane  
  
 Kwalifikator, takich jak **const**, jest stosowany do typu funkcji zdefiniowanych przez `typedef`.  
  
## <a name="example"></a>Przykład  
  
```  
// C4180.cpp  
// compile with: /W1 /c  
typedef int FuncType(void);  
  
// the const qualifier cannot be applied to the  
// function type FuncType  
const FuncType f;   // C4180  
```