---
title: "C2012 błąd kompilatora | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2012
dev_langs: C++
helpviewer_keywords: C2012
ms.assetid: 9f0d8162-c0b3-4234-a41f-836fdb75c84e
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 2e83597ba9224ab6cf5c70b319ff50348bd9135f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2012"></a>C2012 błąd kompilatora
Brak nazwy następujących "<"  
  
 `#include` Dyrektywy brakuje wymaganego pliku.  
  
 Poniższy przykład generuje C2012:  
  
```  
// C2012.cpp  
#include <   // C2012 include the filename to resolve  
```  
  
 Możliwe rozwiązanie:  
  
```  
// C2012b.cpp  
// compile with: /c  
#include <stdio.h>  
```