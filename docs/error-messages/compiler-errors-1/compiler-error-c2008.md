---
title: C2008 błąd kompilatora | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2008
dev_langs:
- C++
helpviewer_keywords:
- C2008
ms.assetid: e748ccbe-ffd4-4008-aca7-e53c25225209
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 88dcbc88b50ee46b406d383ec36e1fed167eca05
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
ms.locfileid: "33165522"
---
# <a name="compiler-error-c2008"></a>C2008 błąd kompilatora
"znak": nieoczekiwany w definicji makra  
  
 Pojawi się natychmiast po nazwie makra. Aby rozwiązać problem, musi istnieć spację po nazwie makra.  
  
 Poniższy przykład generuje C2008:  
  
```  
// C2008.cpp  
#define TEST1"mytest1"    // C2008  
```  
  
 Możliwe rozwiązanie:  
  
```  
// C2008b.cpp  
// compile with: /c  
#define TEST2 "mytest2"  
```