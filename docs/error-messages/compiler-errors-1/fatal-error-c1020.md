---
title: "Błąd krytyczny C1020 | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C1020
dev_langs: C++
helpviewer_keywords: C1020
ms.assetid: 42f429e2-5e3b-4086-a10d-b99e032e51c5
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: c2689b2526b2cf9dc513052e292aca429113c129
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/24/2017
---
# <a name="fatal-error-c1020"></a>Błąd krytyczny C1020
Nieoczekiwany #endif  
  
 `#endif` Dyrektywy nie posiada odpowiadającego `#if`, `#ifdef`, lub `#ifndef` dyrektywy. Należy się, że każdy `#endif` ma pasującego dyrektywy.  
  
 Poniższy przykład generuje C1020:  
  
```  
// C1020.cpp  
#endif     // C1020  
```  
  
 Możliwe rozwiązanie:  
  
```  
// C1020b.cpp  
// compile with: /c  
#if 1  
#endif  
```