---
title: Błąd krytyczny C1103 | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1103
dev_langs:
- C++
helpviewer_keywords:
- C1103
ms.assetid: 9d276939-9c47-4235-9d20-76b8434f9731
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 19f991fd7449eda11651dcca4adc73190e276e35
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
ms.locfileid: "33226078"
---
# <a name="fatal-error-c1103"></a>Błąd krytyczny C1103
krytyczny błąd importu progid: "komunikat"  
  
 Kompilator wykrył problem Importowanie biblioteki typów.  Na przykład nie można określić biblioteki typów z progid i również określić `no_registry`.  
  
 Aby uzyskać więcej informacji, zobacz [#import — dyrektywa](../../preprocessor/hash-import-directive-cpp.md).  
  
 Poniższy przykład wygeneruje C1103:  
  
```  
// C1103.cpp  
#import "progid:a.b.id.1.5" no_registry auto_search   // C1103  
```