---
title: Błąd krytyczny NMAKE U1001 | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- U1001
dev_langs:
- C++
helpviewer_keywords:
- U1001
ms.assetid: 5d7da559-6cbd-44d6-848c-aaf54cae0d1a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 68699a235f461a0f5550802cc009d345ecdba7c4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/04/2018
---
# <a name="nmake-fatal-error-u1001"></a>Błąd krytyczny NMAKE U1001
Błąd składni: niedozwolony znak "character" w makrze  
  
 Podany znak pojawia się w makrze, ale nie jest literą, cyfrą lub podkreślenia.  
  
 Przyczyną tego błędu może być brak dwukropka w rozwinięciu makra:  
  
```  
syntax error : illegal character '=' in macro  
```