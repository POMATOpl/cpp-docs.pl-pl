---
title: "Kompilatora (poziom 1) ostrzeżenie C4185 | Dokumentacja firmy Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4185
dev_langs: C++
helpviewer_keywords: C4185
ms.assetid: 37e7063a-35b1-4e05-ae31-e811dced02b9
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: c3fde7c9cf849006e55a3b1f3c54926597bc0fdc
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4185"></a>Kompilator C4185 ostrzegawcze (poziom 1)
#import nieznany atrybut 'attribute' zostanie zignorowany  
  
 Ten atrybut nie jest prawidłowym atrybutem `#import`. Jest on ignorowany.  
  
## <a name="example"></a>Przykład  
  
```  
// C4185.cpp  
// compile with: /W1 /c  
#import "stdole2.tlb" no_such_attribute   // C4185  
```